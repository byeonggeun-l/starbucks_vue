<template>
  <ul
    class="main-menu"
  >
    <li
      v-for="(Item, Index) in this.items"
      :key="Index"
      class="item"
    >
      <div class="item__name">
        {{ Item.itemMainTitle }}
      </div>
      <div class="item__contents">
        <div class="contents__menu">
          <ul class="inner">
            <li
              v-for="(SubItem, SubItemsIndex) in Item.items"
              :key="SubItemsIndex"
            >
              <h4>{{ SubItem.itemSubTitle }}</h4>
              <ul>
                <li
                  v-for="(SubItemArray, SubItemArrayIndex) in SubItem.items"
                  :key="SubItemArrayIndex"
                >
                  {{ SubItemArray }}
                </li>
              </ul>
            </li>
          </ul>
        </div>
        <div class="contents__texture">
          <div class="inner">
            <div
              v-for="(TextureItem, TextureItemIndex) in Item.texture"
              :key="TextureItemIndex"
              class="inner__items"
            >
              <h4>{{ TextureItem.title }}</h4>
              <p>{{ TextureItem.content }}</p>
            </div>
          </div>
        </div>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  name: "HeaderMainMenu",  
  props: {
    items: {
      type: Array,
      required: true
    },
  },
 
}
</script>

<style>
.main-menu {
  position: absolute;
  bottom: 0;
  right: 0;
  z-index: 1;
  display: flex;
}
.main-menu .item__name {
  padding: 10px 20px 34px 20px;
  font-family: Arial, sans-serif;
  font-size:  13px;
}
.main-menu .item:hover .item__name {
  background-color: #2c2a29;
  color:#669900;
  border-radius: 6px 6px 0 0;
}
.main-menu .item .item__contents {
  width: 100%;
  position: fixed;
  left: 0;
  display: none;
}
.main-menu .item:hover .item__contents {
  display: block;
}
.main-menu .item .item__contents .contents__menu {
  background-color: #2c2a29;
}
.main-menu .item .item__contents .contents__menu > ul {
  display:flex;
  padding: 20px 0;
}
.main-menu .item .item__contents .contents__menu > ul  > li {
    width: 220px;
}
.main-menu .item .item__contents .contents__menu > ul > li h4 {
  padding: 3px 0 12px 0;
  font-size: 14px;
  color: #fff;
}
.main-menu .item .item__contents .contents__menu > ul > li ul li {
  padding: 5px 0;
  font-size: 12px;
  color: #999;
  cursor: pointer;
}
.main-menu .item .item__contents .contents__menu > ul > li ul li:hover {
  color:#669900;
}
.main-menu .item .item__contents .contents__texture {
  padding: 26px 0;
  font-size: 12px;
  background-image: url("../assets/images/main_menu_pattern.jpg");
}
.main-menu .item .item__contents .contents__texture h4 {
  color: #999;
  font-weight: 700;
}
.main-menu .item .item__contents .contents__texture p {
  color: #669900;
  margin: 4px 0 14px;
  font-size: 12px;
}
</style>