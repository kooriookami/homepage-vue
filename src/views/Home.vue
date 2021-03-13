<template>
    <div class="home-container">
        <!--显示或者隐藏动画-->
        <div v-show="visibleAnime" class="anime">
            <el-image :src="require('@/assets/image/paw.png')" class="paw" draggable="false"></el-image>
            <i class="fal fa-mars mars"></i>
            <i class="far fa-circle circle"></i>
        </div>
        <!--显示或者隐藏一键置顶-->
        <div v-show="visibleArrow" @click="arrow">
            <i class="fa fa-arrow-circle-up arrow"></i>
        </div>
        <header>
            <div class="head-container">
                <h1>kooriookami</h1>
                <p>喜欢写点实用又美观的小页面。</p>
                <p>还要学很多新东西。</p>
                <p>总想学以致用。</p>
                <div class="head-icon">
                    <a href="https://github.com/kooriookami" target="_blank">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="mailto:bingshuanglingluo@163.com">
                        <i class="fas fa-envelope"></i>
                    </a>
                </div>
            </div>
        </header>
        <main>
            <div class="toggle">
                <i class="far fa-toggle-on" v-show="toggleOn" @click="toggle"></i>
                <i class="far fa-toggle-off" v-show="!toggleOn" @click="toggle"></i>
            </div>
            <div class="main-container">
                <div>
                    <h2><i class="fa fa-archive"></i>项目作品</h2>
                </div>
                <el-row :gutter="50">
                    <el-col :span="span">
                        <el-card shadow="hover">
                            <a href="https://tools.kooriookami.top" target="_blank">
                                <el-image :src="require('@/assets/image/tools.png')"></el-image>
                                <h3>网页小工具</h3>
                            </a>
                            <p>一个用 Vue 实现的开源网页小工具，不定期更新，欢迎到 github 给颗star</p>
                            <span>#<span class="vue">Vue.js</span></span>
                            <span>#<span class="html">Canvas</span></span>
                            <span>#<span class="element">Element Plus</span></span>
                        </el-card>
                    </el-col>
                    <el-col :span="span">
                        <el-card shadow="hover">
                            <a href="https://designer.kooriookami.top" target="_blank">
                                <el-image :src="require('@/assets/image/designer.png')"></el-image>
                                <h3>页面设计器</h3>
                            </a>
                            <p>页面设计器是一个拖拽式页面生成引擎，以 JSON 格式存储页面数据。</p>
                            <span>#<span class="vue">Vue.js</span></span>
                            <span>#<span class="html">Vue.Draggable</span></span>
                            <span>#<span class="css">Vant</span></span>
                            <span>#<span class="element">Element Plus</span></span>
                        </el-card>
                    </el-col>
                    <el-col :span="span">
                        <el-card shadow="hover">
                            <a href="https://deal.kooriookami.top" target="_blank">
                                <el-image :src="require('@/assets/image/deal.png')"></el-image>
                                <h3>校园搜（毕业设计）</h3>
                            </a>
                            <p>校园搜（CampuSearch），一个校园间的二手货交易网站,只需搜寻你想要的。</p>
                            <span>#<span class="vue">Vue.js</span></span>
                            <span>#<span class="spring-boot">Spring Boot</span></span>
                            <span>#<span class="mysql">MySQL</span></span>
                            <span>#<span class="element">element-UI</span></span>
                        </el-card>
                    </el-col>
                    <el-col :span="span">
                        <el-card shadow="hover">
                            <a href="https://danmaku.kooriookami.top" target="_blank">
                                <el-image :src="require('@/assets/image/danmaku.png')"></el-image>
                                <h3>弹幕主页</h3>
                            </a>
                            <p>一个可以收发弹幕的动态页面。通过 js 控制弹幕的速度，用户还可以选择弹幕的颜色。</p>
                            <span>#<span class="vue">Vue.js</span></span>
                            <span>#<span class="spring-boot">Spring Boot</span></span>
                            <span>#<span class="mysql">MySQL</span></span>
                            <span>#<span class="element">element-UI</span></span>
                        </el-card>
                    </el-col>
                    <el-col :span="span">
                        <el-card shadow="hover">
                            <a href="https://www.kooriookami.top/nethardyun" target="_blank">
                                <el-image :src="require('@/assets/image/nethardyun.png')"></el-image>
                                <h3>网难云主页</h3>
                            </a>
                            <p>一个仿照网易云主页的静态页面。包含注册和登陆页面，使用了栅格布局。</p>
                            <span>#<span class="vue">Vue.js</span></span>
                            <span>#<span class="html">html</span></span>
                            <span>#<span class="css">css</span></span>
                            <span>#<span class="element">element-UI</span></span>
                        </el-card>
                    </el-col>
                    <el-col :span="span">
                        <el-card shadow="hover">
                            <a href="https://bilibili.kooriookami.top" target="_blank">
                                <el-image :src="require('@/assets/image/bilibili.png')"></el-image>
                                <h3>仿B站主页</h3>
                            </a>
                            <p>一个仿照B站主页的静态页面。使用 vue-cli 开发，需挂载服务器运行。</p>
                            <span>#<span class="vue">Vue.js</span></span>
                            <span>#<span class="webpack">webpack</span></span>
                            <span>#<span class="html">html</span></span>
                            <span>#<span class="css">css</span></span>
                            <span>#<span class="element">element-UI</span></span>
                        </el-card>
                    </el-col>
                    <el-col :span="24" v-show="showMore">
                        <el-card shadow="hover">
                            <a href="javascript:" @click="showMore=!showMore">
                                <p class="show-more">显示更多<i class="fa fa-chevron-down"></i></p>
                            </a>
                        </el-card>
                    </el-col>
                    <el-col :span="24" v-show="!showMore">
                        <el-card shadow="hover">
                            <div class="more-main">
                                <a v-for="(item,index) in moreList" :href="item.link" target="_blank">
                                    <div class="number">{{index + 1}}</div>
                                    <p>{{item.title}}</p>
                                </a>
                            </div>
                            <a href="javascript:" @click="showMore=!showMore">
                                <p class="show-more">收起更多<i class="fa fa-chevron-up"></i></p>
                            </a>
                        </el-card>
                    </el-col>
                </el-row>
            </div>
        </main>
        <footer>
            <div class="foot-container">
                <p class="copyright">Copyright © 2018 kooriookami. All Rights Reserved.</p>
                <a class="beian" href="https://beian.miit.gov.cn" target="_blank">苏ICP备18056833号</a>
            </div>
        </footer>
    </div>
</template>

<script>
    export default {
        name: 'Home',
        data() {
            return {
                visibleAnime: true,
                toggleOn: true,
                visibleArrow: false,
                showMore: true,
                span: 12,
                moreList: require('@/assets/json/more-list.json')
            };
        },
        mounted() {
            window.onscroll = () => {
                this.visibleArrow = document.documentElement.scrollTop || window.pageYOffset || document.body.scrollTop;
            };
            this.setSpan();
            addEventListener('resize', this.setSpan);
        },
        unmounted() {
            removeEventListener('resize', this.setSpan);
        },
        methods: {
            setSpan() {
                if (document.body.clientWidth < 760) {
                    this.span = 24;
                } else {
                    this.span = 12;
                }
            },
            toggle() {
                this.visibleAnime = !this.visibleAnime;
                this.toggleOn = !this.toggleOn;
            },
            arrow() {
                let scrollTop = document.documentElement.scrollTop || window.pageYOffset || document.body.scrollTop;
                let timer = setInterval(() => {
                    scrollTop -= 150;
                    scrollTo(0, scrollTop);
                    if (scrollTop <= 0) {
                        clearInterval(timer);
                    }
                }, 10);
            }
        }
    };
</script>

<style lang="scss" scoped>
    .home-container {
        background-image: url("../assets/image/texture.png");
        overflow: hidden;

        .anime {
            position: relative;
        }

        header {
            background-color: rgba(255, 255, 255, 0.2);
        }

        .head-container {
            max-width: 960px;
            margin: 0 auto;
            padding: 80px 15px;
        }

        .head-container h1 {
            margin: 0 auto 15px;
        }

        .head-container p {
            margin: 0 auto;
            line-height: 36px;
        }

        .head-icon {
            margin-top: 30px;
            display: flex;
            flex-wrap: wrap;

            a {
                margin-right: 15px;

                i {
                    font-size: 24px;
                }
            }
        }

        main {
            background-color: rgba(129, 199, 212, 0.2);
        }

        .main-container {
            max-width: 960px;
            margin: 0 auto;
            padding: 80px 15px;
        }

        .main-container i {
            margin-right: 10px;
        }

        .main-container h2 {
            font-size: 16px;
            margin: 0;
        }

        footer {
            background-color: rgba(129, 199, 212, 0.2);
        }

        .foot-container {
            overflow: hidden;
            max-width: 960px;
            margin: 0 auto;
            padding: 0 15px 80px;
        }

        .el-row {
            margin-top: 30px;

            .el-col {
                margin-bottom: 30px;
            }
        }

        a {
            text-decoration: none;
            color: black;
        }

        a:hover {
            color: #00a1d6;
        }

        .el-card img {
            width: 100%;
        }

        .el-card p {
            line-height: 28px;
        }

        .el-card .show-more {
            margin: 0;
            text-align: center;
        }

        .el-card .show-more i {
            margin-left: 10px;
        }

        .el-card span {
            font-size: 14px;
        }

        .el-card .more-main {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }

        .el-card .more-main a {
            width: 300px;
            display: flex;
            flex-grow: 1;
            align-items: center;
            margin-bottom: 10px;
        }

        .el-card .more-main a:nth-child(odd) {
            margin-right: 70px;
        }

        .el-card .more-main a p {
            margin: 0;
        }

        .number {
            text-align: center;
            color: white;
            font-size: 14px;
            line-height: 20px;
            border-radius: 5px;
            background: #00a1d6;
            width: 20px;
            height: 20px;
            margin-right: 10px;
        }

        .vue {
            color: #2CA58D;
            margin-right: 10px;
        }

        .html {
            color: #FF7700;
            margin-right: 10px;
        }

        .css {
            color: #067BC2;
            margin-right: 10px;
        }

        .js {
            color: #F3C969;
            margin-right: 10px;
        }

        .element {
            color: #409eff;
            margin-right: 10px;
        }

        .webpack {
            color: #006a86;
            margin-right: 10px;
        }

        .spring-boot {
            color: #6db33f;
            margin-right: 10px;
        }

        .mysql {
            color: #f29221;
            margin-right: 10px;
        }

        .copyright {
            margin: 0;
            font-size: 14px;
            text-align: center;
            color: #999999;
        }

        .beian {
            margin-top: 20px;
            display: block;
            font-size: 14px;
            text-align: center;
            color: #999999;
        }

        .white {
            color: white;
        }

        .paw {
            z-index: 0;
            position: absolute;
            opacity: 0.5;
            animation-name: paw;
            animation-duration: 15s;
            animation-iteration-count: infinite;
            animation-direction: alternate;
            animation-timing-function: linear;
        }

        .mars {
            z-index: 0;
            font-size: 80px;
            color: #00a1d6;
            position: absolute;
            opacity: 0.5;
            animation-name: mars;
            animation-duration: 25s;
            animation-iteration-count: infinite;
            animation-direction: alternate;
            animation-timing-function: linear;
        }

        .circle {
            z-index: 0;
            font-size: 80px;
            color: #41b883;
            position: absolute;
            opacity: 0.5;
            animation-name: circle;
            animation-duration: 5s;
            animation-iteration-count: infinite;
            animation-timing-function: ease-in;
        }

        .toggle {
            float: right;
            font-size: 40px;
            color: rgba(129, 199, 212, 0.5);
            cursor: pointer;
            margin-right: 10px;
        }

        .toggle:hover, .arrow:hover {
            color: rgba(129, 199, 212, 1);
        }

        .arrow {
            z-index: 2;
            color: rgba(129, 199, 212, 0.5);
            font-size: 54px;
            position: fixed;
            cursor: pointer;
            bottom: 15px;
            right: 15px;
        }

        @keyframes paw {
            from {
                transform: translate(-100px, 500px) rotate(-60deg);
            }
            to {
                transform: translate(800px, -100px) rotate(300deg);
            }
        }

        @keyframes mars {
            from {
                transform: translate(1000px, -100px) rotate(0);
            }
            to {
                transform: translate(2000px, 800px) rotate(500deg);
            }
        }

        @keyframes circle {
            from {
                transform: translate(55vw, 550px);
            }
            to {
                transform: translate(55vw, -100px);
            }
        }
    }
</style>
