<template>
    <div>
        <v-container>
        <h2 class="board_title">글쓰기</h2>
        <board-register-form/>
        </v-container>
    </div>
</template>

<script>
import BoardRegisterForm from '@/components/board/free/BoardRegisterForm.vue'

export default {
    name: 'BoardRegisterPage',
    components: {
        BoardRegisterForm
    }
}
</script>

<style scoped>
.board_title {
    font-size: 32px;
    font-weight: 700;
    line-height: 32px;
    color: #333d4b;
    margin-bottom: 60px;
}
</style>