<template>
  <li>
    <base-card>
      <template #default>
        <header>
          <h3>{{ title }}</h3>
          <base-button mode="flat" @click="delRes(id)"> <template #default> Delete </template> </base-button>
        </header>
        <p>{{ description }}</p>
        <nav>
          <a :href="link">View Resource</a>
        </nav>
      </template>
    </base-card>
  </li>
</template>
<script>
export default {
  props: ['id','title', 'description', 'link'],
  inject:['delRes']
};
</script>

<style>
li {
  margin: auto;
  max-width: 40rem;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h3 {
  font-size: 1.25rem;
  margin: 0.5rem 0;
}

p {
  margin: 0.5rem 0;
}

a {
  text-decoration: none;
  color: #ce5c00;
}

a:hover,
a:active {
  color: #c89300;
}
</style>
