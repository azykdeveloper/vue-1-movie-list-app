<template>
  <li
    class="list-group-item d-flex justify-content-between"
    :class="[{ like: movie.like }, { favourite: movie.favourite }]"
    
  >
    <span @click="$emit('onToggle', { id: movie.id, prop: 'like'})" class="list-group-item-label">{{ movie.name }}</span>
    <input type="text" class="list-group-item-input" :value="movie.viewers"  />
    <div class="d-flex justify-content-center align-items-center">
      <button @click="$emit('onToggle', { id: movie.id, prop: 'favourite'})" type="button" class="btn-cookie btn-sm" >
        <i class="fas fa-cookie"></i>
      </button>
      <button @click="$emit('onRemove', movie.id)" type="button" class="btn-trash btn-sm">
        <i class="fas fa-trash"></i>
      </button>
      <i class="fas fa-star"></i>
    </div>
  </li>
</template>

<script>
export default {
  props: {
    movie: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.list-group-item {
  padding: 15px 20px;
  border-bottom: 1px solid #3d5a80;
}
.list-group-item:last-child {
  border-bottom: none;
}
.list-group-item span {
  width: 550px;
  font-size: 18px;
  cursor: pointer;
  line-height: 35px;
}
.list-group-item input {
  font-size: 18px;
  text-align: center;
  border: none;
  outline: none;
}
.list-group-item button {
  width: 35px;
  height: 35px;
  margin: 3px;
  font-size: 17px;
  border: none;
  cursor: pointer;
}
.list-group-item .btn-cookie {
  color: #e09f3e;
}
.list-group-item .btn-trash {
  color: #e5383b;
}
.list-group-item .fa-star {
  width: 35px;
  height: 35px;
  margin: 3px;
  font-size: 17px;
  color: #ffd700;
  transition: 0.3s all ease;
  text-align: center;
  line-height: 35px;
  transform: translateX(40px);
  opacity: 0;
}
.list-group-item.like .fa-star {
  transform: translateX(0);
  opacity: 1;
}
.list-group-item.favourite .list-group-item-label,
.list-group-item.favourite .list-group-item-input {
  color: #e09f3e;
}
</style>
