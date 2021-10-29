<template>
    <div v-if="code === 0">
      <p>{{ description }}</p>
    </div>
    <div v-else-if="code === 1">
      <p>{{ description }}</p>
      <p>hello??</p>
    </div>
    <div v-else-if="code === 2">
      <p>{{ description }}</p>
    </div>
    <div v-else-if="code === 3">
      <p>{{ description }}</p>
    </div>
    <div v-else-if="code === 10">
      <p> description </p>
    </div>
    <div v-else-if="code === 21">
      <p>this the third</p>
    </div>
    <div v-else-if="code === 22">
      <p>this the third</p>
    </div>
    <div v-else-if="code === 24">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 45">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 50">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 51">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 60">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 61">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 62">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 64">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 65">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 80">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 81">
      <p>this the third</p>
    </div>
    <div v-else-if="post.wx_code === 82">
      <p>this the third</p>
    </div>
</template>