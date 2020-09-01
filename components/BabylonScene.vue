<template>
  <div>
    <div id="loadingScreen"></div>
    <canvas id="renderCanvas" class="babylon-scene w-full"></canvas>
  </div>
</template>

<script>
import * as BABYLON from 'babylonjs';
import 'babylonjs-loaders'

export default {
  name: 'babylon-scene',
  mounted() {
    var canvas = document.getElementById('renderCanvas')
    var engine = new BABYLON.Engine(canvas, true);

    // Remove default
    var loadingScreenDiv = window.document.getElementById("loadingScreen");
    function customLoadingScreen() {
        console.log("customLoadingScreen creation")
    }
    customLoadingScreen.prototype.displayLoadingUI = function () {
        console.log("customLoadingScreen loading")
        // loadingScreenDiv.innerHTML = "loading";
    };
    customLoadingScreen.prototype.hideLoadingUI = function () {
        console.log("customLoadingScreen loaded")
        // loadingScreenDiv.style.display = "none";
    };
    var loadingScreen = new customLoadingScreen();
    engine.loadingScreen = loadingScreen;

    engine.displayLoadingUI();
    
        var createScene = function () {

            var scene = new BABYLON.Scene(engine);

            // bg transparent
            scene.clearColor = new BABYLON.Color4

            // Add a camera to the scene and attach it to the canvas
            var camera = new BABYLON.ArcRotateCamera("Camera", Math.PI / 2, Math.PI / 2, 2, new BABYLON.Vector3(0,0,.25), scene);
            camera.attachControl(canvas, true);


            // Add lights to the scene
            var light1 = new BABYLON.HemisphericLight("light1", new BABYLON.Vector3(1, 1, 0), scene);
            var light2 = new BABYLON.PointLight("light2", new BABYLON.Vector3(0, 1, -1), scene);

            // The first parameter can be used to specify which mesh to import. Here we import all meshes
            BABYLON.SceneLoader.Append("/mesh_models/", "statue_woman_model.glb", scene, function (newMeshes) {
                scene.createDefaultCameraOrLight(true, true, true);
                scene.activeCamera.useAutoRotationBehavior = true;
                scene.activeCamera.lowerRadiusLimit = 4;
                scene.activeCamera.upperRadiusLimit = 5;
                
                scene.activeCamera.alpha = 0.8;

                var helper = scene.createDefaultEnvironment({
                    skyboxSize: 1500,
                    groundShadowLevel: 0.5,
                });       

                helper.setMainColor(new BABYLON.Color3(0,0,0));

                scene.environmentTexture.lodGenerationScale = 0.6;

            });

            return scene;
        };

        var scene = createScene();

        // Register a render loop to repeatedly render the scene
        engine.runRenderLoop(function () {
                scene.render();
        });

        // Watch for browser/canvas resize events
        window.addEventListener("resize", function () {
                engine.resize();
        });
  }
}
</script>

<style class="scss">
  .babylon-scene {
    margin-left: 16rem;
    min-height: 80vh;
  }

  @media screen and (max-width: 767px) {
    .babylon-scene {
      margin-left: 0;
      min-height: 80vh;
    }
  }

  #renderCanvas {
    background: transparent;
    background: #05070c;
    background: rgb(5, 7, 12);
  }

</style>