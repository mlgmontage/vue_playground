<template>
  <div>
    <h2>Vue forms</h2>
    <form>
      <label>
        <input v-model="name" placeholder="type your name" type="text" />
        {{name}}
      </label>
      <br />
      <label>
        <input v-model="surname" placeholder="type your surname" type="text" />
        {{surname}}
      </label>
      <br />
      <label>
        Are you member?
        <input type="checkbox" v-model="isMember" />
        {{ isMember ? 'yes' : 'no'}}
      </label>
      <br />
      <label>
        enter your favorite controllers
        <label
          v-for="(controller, index) in controllers"
          :key="index"
        >
          <input type="checkbox" v-model="selectedControllers" :value="controller" />
          {{ controller}}
        </label>
        {{ selectedControllers }}
      </label>
      <label>
        <select v-model="selectedController" multiple>
          <option disabled>Please select one</option>
          <option v-for="(controller, index) in controllers" :key="index">{{ controller}}</option>
        </select>
        {{ selectedController }}
      </label>
      <label>
        <label v-for="(editor, inx) in editors" :key="inx">
          <input v-model="favEditor" type="radio" name="mode" :value="editor" />
          {{ editor}}
        </label>
        {{ favEditor}}
      </label>
    </form>
  </div>
</template>

<script>
export default {
  name: "forms",
  data() {
    return {
      name: "",
      surname: "",
      isMember: false,
      selectedControllers: [],
      selectedController: [],
      favEditor: "",
      controllers: [
        "keyboard",
        "joystick",
        "mouse",
        "arcade stick",
        "dualshock"
      ],
      editors: ["vscode", "atom", "sublime text", "vim", "emacs"]
    };
  }
};
</script>

<style scoped>
label {
  display: block;
}
</style>