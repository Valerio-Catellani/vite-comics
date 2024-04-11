<template>
    <div class="highlight-card d-flex justify-content-center pb-1 pt-5 mb-5">
        <div class="img-container">
            <img :src="img" class="img-fluid w-100" :alt="title">
        </div>
        <div class="card-info px-3 pb-3">
            <div class="mb-3">
                <h5 class="card-title text-center display-5">{{ title }}</h5>
                <p class="card-text overflow-y-auto">{{ text }} </p>
            </div>
            <ul class="list-group list-group-flush">
                <li class="list-group-item">Cost: {{ price }} $</li>
                <li class="list-group-item">Disponibility: {{ disponibiliy }}</li>
                <li class="list-group-item">Series: {{ series }}</li>
            </ul>
            <div class="d-flex gap-3 justify-content-center my-3">
                <a href="#" class="card-link" @click.prevent>Buy it Now</a>
                <a href="#" class="card-link" @click.prevent>Add to Cart </a>
                <a href="#" class="card-link text-danger" @click.prevent="$emit('close-highlight')">Close </a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardHighlightedComponent',
    props: {
        title: {
            type: String,
            required: true
        },
        img: {
            type: String,
            required: true
        },
        price: {
            type: String,
            default: 'No information'
        },
        disponibiliy: {
            type: String,
            default: 'Available'
        },
        series: {
            type: String,
            default: 'DC Comics'

        }
    },
    data() {
        return {
            text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptas officia iure, dolorem ad in atque, rerum odio eius sed quasi amet similique tempore eum vel illum quisquam numquam deleniti modi ratione facilis alias tenetur sit repellat exercitationem. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nobis, autem pariatur quod doloremque laudantium et? Facilis sapiente consequatur natus unde. Odio ducimus hic fuga maxime, quos praesentium iste ut aliquid. Aut culpa a debitis, molestias necessitatibus sit error quod eum! Deserunt nam excepturi, illum impedit reprehenderit eos asperiores soluta recusandae.  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nobis, autem pariatur quod doloremque laudantium et? Facilis sapiente consequatur natus unde. Odio ducimus hic fuga maxime, quos praesentium iste ut aliquid. Aut culpa a debitis, molestias necessitatibus sit error quod eum! Deserunt nam excepturi, illum impedit reprehenderit eos asperiores soluta recusandae. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nobis, autem pariatur quod doloremque laudantium et? Facilis sapiente consequatur natus unde. Odio ducimus hic fuga maxime, quos praesentium iste ut aliquid. Aut culpa a debitis, molestias necessitatibus sit error quod eum! Deserunt nam excepturi, illum impedit reprehenderit eos asperiores soluta recusandae.'
        }
    },

}
</script>

<style lang="scss" scoped>
@use '../../assets/styles/partials/variables' as *;

.highlight-card {
    overflow: hidden;
}

.img-container {
    width: 300px;
    height: 100%;
    overflow: hidden;
}

.card-info {
    max-width: 50%;
    height: 100%;
    overflow: hidden;

    .card-text {
        max-height: 150px;
    }

    a {
        text-decoration: none;
    }
}
</style>