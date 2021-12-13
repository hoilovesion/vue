<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <form>
      <fieldset>
        <dl>
          <dt><label>이름</label></dt>
          <dd>
            <input type="text" v-model="id" />
            <span class="txt-warning" v-if="id && !idValid">유효하지 않은 아이디입니다.</span>
          </dd>
        </dl>
        <dl>
          <dt><label>생년월일</label></dt>
          <dd>
            <select>
              <option value="">년</option>
            </select>
            <select>
              <option value="">월</option>
            </select>
            <select>
              <option value="">일</option>
            </select>
          </dd>
        </dl>
        <dl>
          <dt>성별</dt>
          <dd><label>남</label><input type="radio" value="M" /> <label>여</label><input type="radio" value="F" /></dd>
        </dl>
        <dl>
          <dt><label>이메일</label></dt>
          <dd><input type="text" /></dd>
        </dl>
        <dl>
          <dt><label>주소</label></dt>
          <dd><input type="text" /></dd>
        </dl>
        <dl>
          <dt><label>휴대전화 번호</label></dt>
          <dd><input type="text" /></dd>
        </dl>
      </fieldset>
    </form>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      id: "",
      password: "",
    };
  },
  computed: {
    idValid() {
      return /^[A-Za-z0-9]+$/.test(this.id);
    },
  },
  watch: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
fieldset {
  max-width: 300px;
  padding: 10px;
  margin: 30px auto;
}
input[type="text"],
select {
  height: 30px;
  padding: 0 10px;
  border: 1px solid #ccc;
}
input[type="text"] {
  width: 100%;
}
select {
  width: 28%;
  margin: 0 5px;
}
dl {
  margin-bottom: 20px;
}
.txt-warning {
  font-size: 11px;
  color: #f00;
}
</style>
