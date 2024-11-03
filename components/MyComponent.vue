<template>
  <div class="main">
    <img
      :style="imgStyles"
      :class="imgFilters"
      v-if="imgVisible"
      src="../assets/map.png"
    />
    <p v-else>Картинка спрятана</p>
    <div>
      <p>Скрипты</p>
      <div class="group-btn">
        <button type="button" @click="imgFilters.sepia = !imgFilters.sepia">
          Сепия
        </button>
        <button @click="imgFilters.border = !imgFilters.border" type="button">
          Рамка
        </button>
        <button type="button" @click="imgFilters.shadow = !imgFilters.shadow">
          Тень
        </button>
      </div>
      <div>
        <p>Размер</p>
        <label>
          Ширина {{ imgFilters.currentWidth }}
          <input
            type="range"
            :value="imgFilters.currentWidth"
            @input="imgFilters.currentWidth = $event.target.value"
            :min="imgSizes.minWidth"
            :max="imgSizes.maxWidth"
          />
        </label>
        <label>
          Высота {{ imgFilters.currentHeight }}
          <input
            type="range"
            :value="imgFilters.currentHeight"
            @input="imgFilters.currentHeight = $event.target.value"
            :min="imgSizes.minHeight"
            :max="imgSizes.maxHeight"
          />
        </label>
      </div>
      <div>
        <label>
          Поворот {{ imgFilters.currentRotate }}
          <input
            type="range"
            :value="imgFilters.currentRotate"
            @input="imgFilters.currentRotate = $event.target.value"
            :min="imgSizes.minRotate"
            :max="imgSizes.maxRotate"
          />
        </label>
      </div>
      <button v-if="imgVisible" @click="imgVisible = !imgVisible">
        Спрятать
      </button>
      <button v-else @click="imgVisible = !imgVisible">Показать</button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'MyComponent',
  data() {
    return {
      imgVisible: true,
      imgFilters: {
        sepia: false,
        border: false,
        shadow: false,
        currentWidth: 200,
        currentHeight: 400,
        currentRotate: 0,
      },
      imgSizes: {
        minWidth: 10,
        maxWidth: 200,
        minHeight: 10,
        maxHeight: 400,
        minRotate: 0,
        maxRotate: 360,
      },
    };
  },
  computed: {
    imgStyles() {
      return {
        width: `${this.imgFilters.currentWidth}px`,
        height: `${this.imgFilters.currentHeight}px`,
        transform: `rotate(${this.imgFilters.currentRotate}deg)`,
      };
    },
  },
};
</script>
<style lang="scss" scoped>
.main {
  display: flex;
  gap: 50px;
  justify-content: center;
  margin-top: 100px;
}
img {
  height: 400px;
  &.border {
    border: 2px solid black;
  }
  &.sepia {
    filter: sepia(100%);
  }
  &.shadow {
    box-shadow: 10px 5px 5px black;
  }
}
button {
  cursor: pointer;
}
label {
  display: flex;
  flex-direction: column;
}
input {
  cursor: pointer;
}
</style>
