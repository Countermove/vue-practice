<template>
  <h1>Hello {{ userName }}</h1>
  <h1 v-text="userName"></h1>
  <p>{{ year }}</p>
  <p>{{ user.name }}</p>
  <p>{{ user.job }}</p>
  <p v-html="button"></p>
  <!-- // -->
  <h1 v-bind:id="dynamicId">This is a title.</h1>
  <a v-bind:href="url">naver</a>
  <img v-bind:src="image.src" v-bind:alt="image.alt" />
  <input v-bind:type="inputType" />
  <p v-bind:style="pStyle">pStyle</p>
  <h2 v-bind:class="textDecoration">line-through</h2>
  <h2 :class="isDone === true ? 'line-through' : 'highlight'">line-through</h2>
  <h1 v-once v-text="user.name"></h1>
  <input type="text" v-model="user.name" />
  <!-- // -->
  <h2 v-if="showName">{{ user.name }} IF</h2>
  <h2 v-show="!showName">{{ user.name }} Show</h2>
  <ul>
    <template v-if="question === 'frontend'">
      <li>Is HTML fun?</li>
      <li>Is CSS fun?</li>
      <li>Is Javascript fun?</li>
    </template>
    <template v-else>
      <li>Is Java fun?</li>
      <li>Is Python fun?</li>
      <li>Is C# fun?</li>
    </template>
  </ul>
  <!-- // -->
  <div>
    {{ fruits }}
  </div>
  <div>
    <ul>
      <li v-for="item in fruits" :key="item">{{ item }}</li>
      <li v-for="(item, index) in fruits" :key="item">
        {{ index + 1 }}. {{ item }}
      </li>
      <!-- mustache 문법 안 수식은 한개씩만 -->
    </ul>
    <h2 v-for="(value, key, index) in user" :key="key">
      {{ index }}. {{ key }} ==> {{ value }}
    </h2>
  </div>
  <!-- // -->
  <div>
    <li>
      <input type="text" v-model="user.name" />
    </li>
  </div>
</template>

<script>
export default {
  name: "Practice",
  data() {
    return {
      userName: "CheckMail",
      year: 2023,
      user: {
        name: " ",
        job: "programmer",
      },
      button: "<button>Click</button>",
      //
      dynamicId: "content",
      url: "https://www.naver.com/",
      image: {
        src: "https://picsum.photos/200/200",
        alt: "random image",
      },
      inputType: "color",
      pStyle: "color: red; font-size: 36px;",
      textDecoration: "line-through",
      isDone: false, //true
      //
      question: "frontend",
      showName: true,
      //
      fruits: ["banana", "strawberry", "apple", "melon"],
      //
    };
  },
};
</script>

<style>
#title {
  color: red;
  background-color: yellow;
}

#content {
  color: blue;
  background: pink;
}

.line-through {
  text-decoration: line-through;
}

.highlight {
  background-color: grey;
}
</style>
