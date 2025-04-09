<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>3D Model Viewer</title>
    <style>
        body { margin: 0; overflow: hidden; }
        canvas { display: block; }
    </style>
</head>
<body>
    <script src="https://cdn.jsdelivr.net/npm/three@0.132.2/build/three.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.132.2/examples/js/loaders/GLTFLoader.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.132.2/examples/js/controls/OrbitControls.js"></script>
    
    <script>
        // 初始化场景、相机和渲染器
        const scene = new THREE.Scene();
        scene.background = new THREE.Color(0xdddddd);
        
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        camera.position.set(0, 0, 5);
        
        const renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        renderer.shadowMap.enabled = true;
        document.body.appendChild(renderer.domElement);
        
        // 添加轨道控制器
        const controls = new THREE.OrbitControls(camera, renderer.domElement);
        controls.enableDamping = true;
        controls.dampingFactor = 0.05;
        
        // 添加灯光
        const ambientLight = new THREE.AmbientLight(0xffffff, 0.5);
        scene.add(ambientLight);
        
        const directionalLight = new THREE.DirectionalLight(0xffffff, 0.8);
        directionalLight.position.set(1, 1, 1);
        directionalLight.castShadow = true;
        scene.add(directionalLight);
        
        // 加载模型
        const loader = new THREE.GLTFLoader();
        
        // 替换为你的模型路径
        const modelUrl = 'path/to/your/model.glb';
        
        loader.load(
            modelUrl,
            function (gltf) {
                const model = gltf.scene;
                scene.add(model);
                
                // 调整模型位置和缩放
                model.position.set(0, 0, 0);
                model.scale.set(1, 1, 1);
                
                // 自动调整相机位置
                const box = new THREE.Box3().setFromObject(model);
                const center = box.getCenter(new THREE.Vector3());
                const size = box.getSize(new THREE.Vector3());
                
                camera.position.copy(center);
                camera.position.z += size.length();
                controls.target.copy(center);
                controls.update();
            },
            undefined,
            function (error) {
                console.error('加载模型出错:', error);
            }
        );
        
        // 窗口大小调整
        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });
        
        // 动画循环
        function animate() {
            requestAnimationFrame(animate);
            controls.update();
            renderer.render(scene, camera);
        }
        
        animate();
    </script>
</body>
</html>
