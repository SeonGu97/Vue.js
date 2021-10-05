<template>
    <div class="home">
        <div class="item-1-wrap">
            <h1> {{ title[0] }} </h1>
            <div class="item-1">
                <div class="img">
                    <img src="../assets/취업사진1.jpg" alt="취업사진">
                </div>
                <div class="information">
                    <div class="box-1">
                        <p v-for="box1 in text_1" :key="box1">
                            {{ box1 }}
                        </p>
                    </div>
                    <div class="box-2">
                        <p v-for="box2 in text_2" :key="box2">
                            {{ box2 }}
                        </p>
                    </div>                    
                </div>
            </div>
        </div>
        <div class="item-2-wrap">
            <h1> {{ title[1] }} </h1>
            <div class="item-2">
                <div class="skills">
                    <i class="fab fa-html5"><p>HTML5</p></i>
                    <i class="fab fa-css3-alt"><p>CSS3</p></i>
                    <i class="fab fa-js-square"><p>Javascript<span>👑</span></p></i>
                    <i class="fab fa-vuejs"><p>Vue3</p></i>
                    <i class="fas fa-image"><p>PhotoShop</p></i>
                </div>
            </div>
        </div>
        <div class="item-3-wrap">
            <h1>템플릿</h1>
            <div class="item-3">
                <ul class="card">
                    <a :href="template.href" target="blank" v-for="template in text_3" :key="template">
                        <div class="top"> {{ template.name }} </div>
                        <div class="bottom"> {{ template.title }} </div>
                    </a>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: ['자기소개', '스킬', '템플릿'],
            text_1: ['이름', '생년월일', '이메일', '전화번호', '거주지', '전공'],
            text_2: ['강선구', '1997.12.06', 'seongu97@naver.com', '010-8929-4934', '충청북도 청주시', '비전공'],
            text_3: [
                { id: 1, name: 'TO-DO-LIST', title: 'JS', href: 'https://seongu97.github.io/study/todolist/index.html'},
                { id: 2, name: 'NULL', title: 'NULL', href: '#'},
                { id: 3, name: 'NULL', title: 'NULL', href: '#'},
                { id: 3, name: 'NULL', title: 'NULL', href: '#'},
            ]
        }
    }
}
</script>