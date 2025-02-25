<template>
<div class="nav-container">
    <div class="progress-bar" :style="{ width: scrollProgress + '%' }"></div>
</div>
</template>

<script>

export default {
    name: 'Nav',
data() {
    return {
    scrollProgress: 0
    };
},
mounted() {
    window.addEventListener('scroll', this.updateScrollProgress);
},
beforeUnmount() {
    window.removeEventListener('scroll', this.updateScrollProgress);
},
methods: {
    updateScrollProgress() {
    const scrollLeft = document.documentElement.scrollLeft;
    const scrollWidth = document.documentElement.scrollWidth - document.documentElement.clientWidth;
    this.scrollProgress = (scrollLeft / scrollWidth) * 100;
    }
}
};
</script>

<style scoped>
.nav-container {
position: fixed;
top: 0;
left: 0;
width: 100%;
height: 5px;
background: rgba(0, 0, 0, 0.1);
z-index: 1000;
}
.progress-bar {
height: 5px;
background: #dcb253;
transition: width 0.1s ease-out;
}
</style>
  