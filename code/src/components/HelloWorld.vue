<template>
  <div>
    <input
      type="text"
      class="S1"
      placeholder="Search for Doctor "
      v-model="term"
      @input="onSearch"
    />
    <br />
    <br />
  </div>
  <table border="5 px" class="table1">
    <tr>
      <th>Doctor Type</th>
      <th>Name</th>
      <th>Degree</th>
      <th>Clinic</th>
    </tr>
    <tr v-for="(item, index) in toDoList" v-bind:key="index">
      <td>{{ item.title }}</td>
      <td>{{ item.name }}</td>
      <td>{{ item.degree }}</td>
      <td>{{ item.clinic }}</td>
    </tr>
  </table>
</template>

<script>
export default {
  data() {
    return {
      toDoList: [
        {
          title: "Cardiologist",
          name: "Dr. Ashok Seth",
          degree: "Master of Surgery",
          clinic: "MG Hospital",
        },
        {
          title: "Dentist",
          name: "Dr Arun Setia",
          degree: "Bachelor of Dental Surgery (BDS)",
          clinic: "AB Hospital",
        },
        {
          title: "ENT Specialist",
          name: "Dr. Shashi Dhar",
          degree: "MS ENT",
          clinic: "Artemis Hospital",
        },
        {
          title: "Orthopaedic surgeons",
          name: "Dr.Mayil Vahanan Natarajan",
          degree: "D. Ortho.",
          clinic: "EF Hospital",
        },
        {
          title: "Paediatrician",
          name: "Dr. Sindhura Munukuntla",
          degree: "MBBS",
          clinic: "GH Hospital",
        },
        {
          title: "Psychiatrists",
          name: "Dr Gorav Gupta",
          degree: "MBBS",
          clinic: "IJ Hospital",
        },
        {
          title: "Oncologist",
          name: "Dr A P Subash Kumar",
          degree: "Doctorate of Medicine",
          clinic: "KL Hospital",
        },
        {
          title: "Neurology",
          name: "Dr Atma Ram Bansal",
          degree: "Doctorate of Medicine",
          clinic: "MN Hospital",
        },
      ],
      items: [],
      term: "",
    };
  },
  mounted() {
    this.items = this.toDoList;
  },
  methods: {
    onSearch() {
      const searchValue = this.term.toLowerCase().trim();
      this.toDoList = this.items.filter((item) => {
        // const title = item.title.toLowerCase();
        const name = item.name.toLowerCase();
        // const clinic = item.clinic.toLowerCase();
        return typeof name === "string" && name.includes(searchValue);
      });
    },
  },
};
</script>

<style scoped>
.table1 {
  margin-left: auto;
  margin-right: auto;
}
.S1 {
  display: block;
  margin-right: auto;
  margin-left: auto;
}
td {
  text-align: center;
  padding: 2px;
}
</style>
