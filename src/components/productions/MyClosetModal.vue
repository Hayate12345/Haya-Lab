<template>
    <div class="modal" v-if="show">
        <div class="modal-dialog-original">
            <div class="modal-content-original">
                <div class="modal-header-original">
                    <h4 class="modal-title fw-bold">{{ title }}</h4>

                    <button type="button" class="close" @click="closeModal">
                        <svg xmlns="http://www.w3.org/2000/svg" width="27" height="27" fill="currentColor"
                            class="bi bi-x fw-bold" viewBox="0 0 16 16">
                            <path
                                d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708z" />
                        </svg>
                    </button>
                </div>

                <div class="modal-body-original">
                    <div class="left-area">
                        <div class="service">
                            <p>
                                {{ explanation1 }}<br><br>
                                {{ explanation2 }}<br>
                            </p>

                            <p class="links">
                                <a href="#" target="_blank">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="15" height="15" fill="currentColor"
                                        class="bi bi-substack" viewBox="0 0 16 16">
                                        <path
                                            d="M15 3.604H1v1.891h14v-1.89ZM1 7.208V16l7-3.926L15 16V7.208H1ZM15 0H1v1.89h14V0Z" />
                                    </svg>
                                    <small> 詳細はこちら</small>
                                </a>
                                <br>
                                <a href="https://github.com/Hayate12345/My_Closet" target="_blank">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="15" height="15" fill="currentColor"
                                        class="bi bi-github" viewBox="0 0 16 16">
                                        <path
                                            d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.012 8.012 0 0 0 16 8c0-4.42-3.58-8-8-8z" />
                                    </svg>
                                    <small> ソースコードはこちら</small>
                                </a>
                                <br>
                                <a href="https://frozen-cove-82653-5359138e2ddd.herokuapp.com/" target="_blank">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="15" height="15" fill="currentColor"
                                        class="bi bi-box-arrow-up-right" viewBox="0 0 16 16">
                                        <path fill-rule="evenodd"
                                            d="M8.636 3.5a.5.5 0 0 0-.5-.5H1.5A1.5 1.5 0 0 0 0 4.5v10A1.5 1.5 0 0 0 1.5 16h10a1.5 1.5 0 0 0 1.5-1.5V7.864a.5.5 0 0 0-1 0V14.5a.5.5 0 0 1-.5.5h-10a.5.5 0 0 1-.5-.5v-10a.5.5 0 0 1 .5-.5h6.636a.5.5 0 0 0 .5-.5z" />
                                        <path fill-rule="evenodd"
                                            d="M16 .5a.5.5 0 0 0-.5-.5h-5a.5.5 0 0 0 0 1h3.793L6.146 9.146a.5.5 0 1 0 .708.708L15 1.707V5.5a.5.5 0 0 0 1 0v-5z" />
                                    </svg>
                                    <small> サイトはこちら</small>
                                </a>
                            </p>
                        </div>

                        <div style="padding-top: 40px;">
                            <h5 class="text-center">制作期間 / 担当範囲</h5>

                            <p class="mt-3 mb-0 pb-0">
                                {{ ProductionScope }}<br>
                                {{ ScopeOfResponsibility }}
                            </p>
                        </div>

                        <div class="technology-used">
                            <h5 class="text-center">使用技術</h5>

                            <p class="mt-3 mb-0 pb-0">
                                {{ TechnologyUsed }}
                            </p>
                        </div>
                    </div>

                    <div class="right-area">
                        <div class="slideshow">
                            <img :src="currentImage" alt="" style="width: 100%;">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'MyClosetModal',
    props: {
        show: Boolean
    },
    data() {
        return {
            title: "MY CLOSET",
            explanation1: "みなさんはファションで悩んだ経験はありませんか？ 「自分に似合う洋服がわからない...」「いつも同じ洋服ばかり着てしまう...」「洋服にそこまで興味がないけど、ダサいとは言われたくない!」このようなファッションに関する悩み、一度は経験したことがあると思います。 そこで作成したサービスがファッションアプリ「MY CLOSET」です。 「MY CLOSET」には、AIがあなたに似合う洋服を提案してくれるAIコーデ提案機能が搭載されています。",
            explanation2: "「MY CLOSET」には、AIコーデ提案機能だけでなく、クローゼット管理機能やコーディネートQ&A機能、ファッションSNS機能など他にも様々な機能が搭載されています。 詳細は下記のリンクで紹介していますので、ぜひご覧ください。",
            ProductionScope: "制作期間：6ヶ月",
            ScopeOfResponsibility: "担当範囲：設計 / プログラミング",
            TechnologyUsed: "HTML / SCSS / Ruby / Ruby on Rails / PostgreSQL / Heroku / Docker / JavaScript / jQuery / Ajax / Git / GitHub / Bootstrap",
            images: [
                "/assets/my_closet/1.png",
                "/assets/my_closet/2.png",
                "/assets/my_closet/3.png",
                "/assets/my_closet/4.png",
                "/assets/my_closet/5.png",
                "/assets/my_closet/6.png",
                "/assets/my_closet/7.png",
            ],
            currentIndex: 0,
            interval: null,
        };
    },
    mounted() {
        window.addEventListener('resize', this.handleResize);
        this.interval = setInterval(this.changeSlide, 5000);
    },
    beforeDestroy() {
        window.removeEventListener('resize', this.handleResize);
    },
    computed: {
        currentImage() {
            return this.images[this.currentIndex];
        },
    },
    methods: {
        closeModal() {
            this.$emit('close');
        },
        changeSlide() {
            this.currentIndex = (this.currentIndex + 1) % this.images.length;
        },
    },
};
</script>

<style scoped>
.modal {
    position: fixed;
    top: 0;
    left: 0;
    margin: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.6);
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: auto;
}

.modal-dialog-original {
    background: #f6f6f6;
    width: 95%;
    border-radius: 10px;
}

.modal-header-original {
    padding: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.modal-body-original {
    padding: 15px;
    overflow-y: auto;
    overflow-y: scroll;
}

.close {
    background-color: #6792c4;
    border: none;
    color: #ffffff;
    border-radius: 50%;
    padding: 6px 6px;
}

.slideshow img {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
    border-radius: 5px;
    box-shadow: 5px 5px 15px 5px rgba(0, 0, 0, 0.4);
}

.links a {
    text-decoration: none;
}

.links svg,
small {
    vertical-align: middle;
}

/* モバイル */
@media (max-width: 767px) {
    .modal-dialog-original {
        height: 80%;
        margin-top: -80px;
    }

    .modal-body-original {
        height: 70vh;
    }

    .technology-used {
        padding-top: 40px;
        padding-bottom: 40px;
    }
}

/* タブレット/デスクトップ */
@media (min-width: 768px) {
    .modal-dialog-original {
        margin-top: -50px;
        height: 80%;
    }

    .modal-body-original {
        display: flex;
        height: 70vh;
    }

    .left-area {
        width: 35%;
        overflow-y: auto;
        overflow-y: scroll;
    }

    .right-area {
        width: 65%;
        padding-left: 30px;
    }

    .technology-used {
        padding-top: 40px;
        padding-bottom: 20px;
    }

    .slideshow {
        max-width: 100%;
        max-height: 100%;
        text-align: center;
    }
}
</style>
