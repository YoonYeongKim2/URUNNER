<template>
    <div class="글작성">
        <h3 style="padding:30px 0px 30px 0px; font-weight:bold" align="left">URUNNER 공지사항</h3>
        <form @submit.prevent="onSubmit">

                <h6 align="left">등록일자 : </h6>
                <b-form-input type="text" :value="notice.regDate" disabled>
                </b-form-input>
               
                <br>

                <h6 align="left">제목 : </h6>
                <b-form-input type="text" v-model="title">
                </b-form-input>
                
                <br>

                <h6 align="left">작성자 : </h6>
                <b-form-input type="text" :value="notice.writer" disabled>
                </b-form-input>
                <br>

                <h6 align="left">내용 : </h6>
                <b-form-textarea
                    id="textarea-rows"
                    placeholder=""
                    rows="8" v-model="content">
                </b-form-textarea>
            <div>

            <div class="버튼" style="padding:20px;">
                <v-btn text color="black" rounded x-large
                        style="padding: 10px; width: 90px;"
                        type="submit">수정완료
                </v-btn>

                <br>

                <router-link style="text-decoration: none; color:black"
                :to="{ name: 'NoticeReadPage', params: { noticeNo: notice.noticeNo.toString() } }">
                    <v-btn text color="black" rounded x-large
                        style="padding: 10px; width: 90px;">
                    취소
                    </v-btn>
                </router-link>
            </div>
            
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: 'NoticeModifyForm',
    props: {
        notice: {
            type: Object,
            required: true
        }
    },
    data () {
        return {
            title: '',
            writer: '',
            content: ''
        }
    },
    methods: {
        onSubmit () {
            var result = confirm('수정 하시겠습니까?')
            if(result) {
                const { title, writer,content } = this
                this.$emit('submit', { title, writer, content })
                }
            }
    },
    created () {
        this.title = this.notice.title
        this.writer = this.notice.writer
        this.content = this.notice.content
    }
}
</script> 

<style scoped>

.글작성 {
  padding:0px 200px 100px 200px;
}
</style>