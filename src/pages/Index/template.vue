<template>
  <div id="index">
    <section class="blog-posts">
      <div class="item" v-for="blog in blogs" :key="blog.id">
        <figure class="avatar">
          <img :src="blog.user.avatar" :alt="blog.user.username">
          <figcaption>{{blog.user.username}}</figcaption> 
        </figure>
        <h3>
          <router-link :to="`/detail/${blog.id}`">{{blog.title}}</router-link>
          <span>{{friendlyDate(blog.createdAt)}}</span>
        </h3> 
        <p>{{blog.description}}</p>
      </div>
    </section>
    <section class="pagination">
      <el-pagination 
        layout="prev, pager, next" 
        :total="total" 
        :current-page="page"
        @current-change="onPageChange">        
      </el-pagination>
    </section>
  </div>
</template>

<script src="./template.js"></script>

<style scoped lang="less" src="./template.less"></style>
