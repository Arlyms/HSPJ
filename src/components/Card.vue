<template>
    <div class="card">
        <div class="card-image">

        </div>
        <div class="card-content">
            <div class="content">
                <h3 class="tittle">{{ tittle }}</h3>
                <p class="description">{{ description }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        tittle: {
            type: String,
            required: true
        },
        description: {
            type: String,
            required: true
        }
    }
    
}
</script>

<style lang="scss" scoped>

.card {
    border: 1px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: box-shadow 0.3s ease;

    &:hover {
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .card-image {
        height: 200px;
        background-color: #f4f4f4;
        background-size: cover;
        background-position: center;
    }

    .card-content {
        padding: 16px;

        .content {
        .title {
            font-size: 1.5em;
            margin-bottom: 0.5em;
        }

        .description {
            font-size: 1em;
            color: #666;
        }
        }
    }
}
</style>