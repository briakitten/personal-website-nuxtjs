<template>
  <div class="my-canvas-wrapper">
    <canvas ref="my-canvas"></canvas>
    <slot></slot>
  </div>
</template>

<script>
// import * as Three from 'Three'

// export default {
//     name: 'ThreeTest',
//     data() {
//         return {
//         camera: null,
//         scene: null,
//         renderer: null,
//         meshes: []
//         }
//     },
//     methods: {
//         init: function() {
//             // const width = 1000;
//             // const height = 150;

//             // this.camera = new Three.PerspectiveCamera( 50, width / height, 0.1, 100 );
//             // this.camera.position.set( 0.5, 1, 2 );
//             // this.camera.lookAt(new Three.Vector3(0.1, 4, 4));

//             // this.scene = new Three.Scene();
//             // this.scene.background = new Three.Color( 0xffffff );

//             // // add the example meshes

//             // const geometries = [
//             //     new Three.BoxGeometry( 0.4, 0.4, 0.4 ),
//             //     new Three.IcosahedronGeometry( 0.3 ),
//             //     new Three.TorusKnotGeometry( 0.4, 0.05, 256, 24, 1, 3 )
//             // ];

//             // const material = new Three.MeshNormalMaterial();

//             // for ( let i = 0, l = geometries.length; i < l; i ++ ) {

//             //     const angle = ( i / l ) * Math.PI * 2;

//             //     const geometry = geometries[ i ];
//             //     const mesh = new Three.Mesh( geometry, material );
//             //     mesh.position.y = 0.1;
//             //     // mesh.position.x = Math.cos( angle ) / 2.0;
//             //     // mesh.position.z = Math.sin( angle ) / 2.0;
//             //     mesh.position.x = 4;
//             //     mesh.position.z = 4;
//             //     this.scene.add( mesh );
//             //     this.meshes.push( mesh );

//             // }

//             // this.renderer = new Three.WebGLRenderer( { antialias: true } );
//             // this.renderer.setSize( width, height );

//             // this.$refs['my-canvas'].appendChild(this.renderer.domElement)

//             this.camera = new Three.PerspectiveCamera( 45, window.innerWidth / window.innerHeight, 1, 2000 );
//             this.camera.position.y = 400;

//             this.scene = new Three.Scene();

//             let object;

//             const ambientLight = new Three.AmbientLight( 0xcccccc, 0.4 );
//             this.scene.add( ambientLight );

//             const pointLight = new Three.PointLight( 0xffffff, 0.8 );
//             this.camera.add( pointLight );
//             this.scene.add( this.camera );

//             const map = new Three.TextureLoader().load( 'textures/uv_grid_opengl.jpg' );
//             map.wrapS = map.wrapT = Three.RepeatWrapping;
//             map.anisotropy = 16;

//             const material = new Three.MeshPhongMaterial( { map: map, side: Three.DoubleSide } );

//             //

//             object = new Three.Mesh( new Three.SphereGeometry( 75, 20, 10 ), material );
//             object.position.set( - 300, 0, 200 );
//             this.scene.add( object );

//             object = new Three.Mesh( new Three.IcosahedronGeometry( 75, 1 ), material );
//             object.position.set( - 100, 0, 200 );
//             this.scene.add( object );

//             object = new Three.Mesh( new Three.OctahedronGeometry( 75, 2 ), material );
//             object.position.set( 100, 0, 200 );
//             this.scene.add( object );

//             object = new Three.Mesh( new Three.TetrahedronGeometry( 75, 0 ), material );
//             object.position.set( 300, 0, 200 );
//             this.scene.add( object );

//             //

//             object = new Three.Mesh( new Three.PlaneGeometry( 100, 100, 4, 4 ), material );
//             object.position.set( - 300, 0, 0 );
//             this.scene.add( object );

//             object = new Three.Mesh( new Three.BoxGeometry( 100, 100, 100, 4, 4, 4 ), material );
//             object.position.set( - 100, 0, 0 );
//             this.scene.add( object );

//             object = new Three.Mesh( new Three.CircleGeometry( 50, 20, 0, Math.PI * 2 ), material );
//             object.position.set( 100, 0, 0 );
//             this.scene.add( object );

//             object = new Three.Mesh( new Three.RingGeometry( 10, 50, 20, 5, 0, Math.PI * 2 ), material );
//             object.position.set( 300, 0, 0 );
//             this.scene.add( object );

//             //

//             object = new Three.Mesh( new Three.CylinderGeometry( 25, 75, 100, 40, 5 ), material );
//             object.position.set( - 300, 0, - 200 );
//             this.scene.add( object );

//             const points = [];

//             for ( let i = 0; i < 50; i ++ ) {

//                 points.push( new Three.Vector2( Math.sin( i * 0.2 ) * Math.sin( i * 0.1 ) * 15 + 50, ( i - 5 ) * 2 ) );

//             }

//             object = new Three.Mesh( new Three.LatheGeometry( points, 20 ), material );
//             object.position.set( - 100, 0, - 200 );
//             this.scene.add( object );

//             object = new Three.Mesh( new Three.TorusGeometry( 50, 20, 20, 20 ), material );
//             object.position.set( 100, 0, - 200 );
//             this.scene.add( object );

//             object = new Three.Mesh( new Three.TorusKnotGeometry( 50, 10, 50, 20 ), material );
//             object.position.set( 300, 0, - 200 );
//             this.scene.add( object );

//             //

//             this.renderer = new Three.WebGLRenderer( { antialias: true } );
//             this.renderer.setPixelRatio( window.devicePixelRatio );
//             this.renderer.setSize( window.innerWidth, window.innerHeight );

//             //

//             this.$refs['my-canvas'].appendChild(this.renderer.domElement)
//         },
//         animate: function() {
//             requestAnimationFrame(this.animate);

//             // this.meshes.forEach( mesh => {

//             //     mesh.rotation.x += 0.01;
//             //     mesh.rotation.y += 0.02;

//             // } );

//             // // set renderer clear alpha
//             // const initialClearAlpha = this.renderer.getClearAlpha();
//             // this.renderer.setClearAlpha( 0 );

//             // // reset and render the normal scene
//             // this.renderer.setRenderTarget( null );
//             // this.renderer.setClearAlpha( initialClearAlpha );

//             // this.renderer.render(this.scene, this.camera);

//             const timer = Date.now() * 0.0001;

//             this.camera.position.x = Math.cos( timer ) * 800;
//             this.camera.position.z = Math.sin( timer ) * 800;

//             this.camera.lookAt( this.scene.position );

//             this.scene.traverse( function ( object ) {

//                 if ( object.isMesh === true ) {

//                     object.rotation.x = timer * 5;
//                     object.rotation.y = timer * 2.5;

//                 }

//             } );

//             this.renderer.render( this.scene, this.camera );
//         },
//     },
//     mounted() {
//         this.init();
//         this.animate();
//     }
// }
</script>

<style>

</style>