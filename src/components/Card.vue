<template>
    <div class="d-flex align-center flex-column">  
        <v-card class="twitter-card"
        width="600"
        :title=title
        :text=content
        >
            <div class="card-footer d-flex align-center">
                <v-btn @click="likeCard"><i class="fas fa-thumbs-up"></i> Лайк {{ likes }}</v-btn>
                <v-btn @click="dislikeCard"><i class="fas fa-thumbs-down"></i> Дизлайк {{ dislikes }}</v-btn>
            </div>
        </v-card>
    </div>
</template>
  
<script lang="ts">
import { defineComponent, PropType, ref } from 'vue';

export default defineComponent({
  props: {
    title: {
      type: String,
      required: true,
    },
    content: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    const likes = ref(0);
    const dislikes = ref(0);

    const likeCard = () => {
      likes.value++;
    };

    const dislikeCard = () => {
      dislikes.value++;
    };

    return {
      likes,
      dislikes,
      likeCard,
      dislikeCard,
    };
  },
});
</script>

<style>
.twitter-card {
    margin: 10px 0;
    border-color: black;
    border-width: 1px;
    max-width: 100%;
}
button {
  margin: 10px 10px;
  cursor: pointer;
}
</style>