<template>
  <section>
    <h3>Añadir Profesor</h3>
    <div><label>Nombre: </label><input type="text" v-model="teacher.name" /></div>
    <div><label>Apellido: </label><input type="text" v-model="teacher.lastname" /></div>
    <div><label>CC: </label><input type="text" v-model="teacher.identification" /></div>
    <div><label>Materias :</label><input type="text" v-model="cource" /><button @click="addCourse">Agregar</button></div>
    <ul>
      <li v-for="(courseT, i) in teacher.courses" :key="i">{{ courseT }}</li>
    </ul>
    <input type="checkbox" v-model="teacher.docs" /> Documentacion Entregada
    <button @click="addTeacher">Add Teacher</button>

    <table>
      <thead>
        <tr>
          <td>Name</td>
          <td>LastName</td>
          <td>Identification</td>
          <td>Courses</td>
          <td>Docs</td>
        </tr>
      </thead>
      <tbody>
        <tr v-for="tch, i in teachers" :key="i">
          <td>{{ tch.name }}</td>
          <td>{{ tch.lastname }}</td>
          <td>{{ tch.identification }}</td>
          <td>
            <ul>
              <li v-for="tchCourses, iC in tch.courses" :key="iC">{{ tchCourses }}</li>
            </ul>
          </td>
          <td>{{ tch.docs }}</td>
        </tr>
      </tbody>
    </table>
  </section>
</template>

<script lang="ts" setup>
import { Ref, ref } from 'vue';

interface ITeacher {
  name: string;
  lastname: string;
  identification: number;
  courses: Array<string>;
  docs: boolean;
}

let teacher: Ref<ITeacher> = ref({
  name: '',
  lastname: '',
  identification: 0,
  courses: [],
  docs: false,
});

let teachers: Ref<Array<ITeacher>> = ref([]);

let cource: Ref<string> = ref('');
let addCourse = () => {
  teacher.value.courses.push(cource.value);
  cource.value = '';
};
let addTeacher = () => {
  teachers.value.push({
    name: teacher.value.name,
    lastname: teacher.value.lastname,
    identification: teacher.value.identification,
    courses: teacher.value.courses,
    docs: teacher.value.docs,
  });
  teacher.value.name = '';
  teacher.value.lastname = '';
  teacher.value.identification = 0;
  teacher.value.courses = [];
  teacher.value.docs = false;
};
</script>

<style scoped></style>
