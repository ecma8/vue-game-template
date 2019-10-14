<template>
    <div class="container">
        <div class="canvas" ref="canvas"></div>
    </div>
</template>

<script>

    import {Application, Container, Graphics, Sprite,Texture, ParticleContainer} from 'pixi.js';
    import {getAnimation, load} from '../../../loader';
    let question;
    let allData;
    export default {
        name: "index",
        data() {
            return {
                number: 0,
            }
        },
        methods: {
            createApp() {
                return new Application({
                    width: 1920,
                    height: 1080,
                    autoSize: true,
                    transparent: true //背景是否设为透明
                })
            }
        },
        created() {
            let loading = document.getElementsByClassName('page-loading')[0];
            loading.style.display = 'block';
        },
        destroyed() {
        },
        mounted() {
            PIXI.sound.stopAll();
            let loading = document.getElementsByClassName('page-loading')[0];
            loading.style.display = 'block';
            window.app = this.createApp();
            app.view.style.width = '19.2rem';
            app.view.style.height = '10.8rem';
            app.view.id = 'canvas';
            window.stage = app.stage;
            const self = this;
            self.$refs.canvas.appendChild(app.view);
            stage.interactive = true;
            load().then(res => {

            })
        }
    }
</script>
<style scoped>
    .canvas {
        width: 19.2rem;
        height: 10.8rem;
        position: absolute;
        left: 50%;
        top: 50%;
        margin-left: -9.6rem;
        margin-top: -5.4rem;
        font-family: "xueersi cuyuan bold";
    }
    canvas{
        font-family: "xueersi cuyuan bold";
    }
    .logo {
        position: absolute;
        z-index: 999;
        left: .5rem;
        bottom: .3rem;
        width: 1.9rem;
    }
</style>