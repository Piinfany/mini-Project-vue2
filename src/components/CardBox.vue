<template>
  <li>
    <img src="https://cdn-icons-png.flaticon.com/128/1326/1326377.png"/>
    <hr/>
    <slot name="card-header"></slot>
    <slot name="card-button"></slot>
    <slot name="card-content"></slot>
  </li>
</template>

<script>
export default {

}
</script>

<style>
li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background: rgb(97, 131, 179);
  padding: 0.5rem;
  color: #fff;
  border-radius: 25px;
}
img {
    width: 100px;
    height: 100px;
}
</style>