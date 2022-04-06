<template>
  <div class="info">
    <div id="functional">
      <button @click="" id="addStudent">Add</button>
      <input
        type="text"
        v-model="addName"
        id="addName"
        placeholder="Enter Student's Name"
      />
      <input
        type="text"
        v-model="addPhone"
        id="addPhone"
        placeholder="Enter Student's Phone"
      />
      <input
        type="text"
        v-model="addEmail"
        id="addEmail"
        placeholder="Enter Student's Email"
      />
      <button @click="" id="removeStudent">Remove</button>
      <input
        type="text"
        v-model="findStudentInput"
        id="findStudentInput"
        placeholder="Enter Student data"
      />
      <button @click="" id="findStudent">Find</button>
    </div>
    <div id="main_cont_wrapper">
      <div id="appSelection">
        <div id="selectionWrapper">
          <div class="selectionHeader">USARB Database</div>
            <div
              id="printStudentsName"
              v-for="printOption in usarbDatabase.length - 1"
              :key="printOption">
              <option @click="printInfo">
                {{ usarbDatabase[printOption].studentName }}
              </option>
            </div>
        </div>
      </div>
      <div id="appPrint">
        <div id="printWrapper">
          <div class="printHeader">Info about person</div>
          <div id="printOption"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      usarbDatabase: [
        {},
        {
          studentName: "John Brown",
          studentPhone: "+373090055900",
          studentEmail: "j.brown@gmail.com",
        },
        {
          studentName: "Eric Hollow",
          studentPhone: "+373060055600",
          studentEmail: "e.hollow@gmail.com",
        },
      ],
      studentName: "",
      studentPhone: "",
      studentEmail: "",
      addName: "",
      addPhone: "",
      addEmail: "",
      findStudentInput: "",
      printOption: 1,
    };
  },
  computed: {},
  methods: {
    addNewStudent() {},
    getValue() {
      return (this.value = this.getItemValue);
    },
    printInfo() {
      this.getValue();
      const printInfoAbout = document.getElementById("printOption");
      this.setAttribute
      printInfoAbout.innerHTML = "";
      printInfoAbout.append(
        this.usarbDatabase[this.value].studentName,
        document.createElement("br")
      );
      printInfoAbout.append(
        this.usarbDatabase[this.value].studentPhone,
        document.createElement("br")
      );
      printInfoAbout.append(
        this.usarbDatabase[this.value].studentEmail,
        document.createElement("br")
      );
    },
  },
};
</script>

<style>
@media (width: 1024px) {
  .info {
    display: flex;
    align-items: center;
  }
}
#selectedStudent {
    display: block;
}
#printStudentsName {
  list-style: none;
}
#main_cont_wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  background-color: rgb(165, 165, 165);
}
#appSelection {
  border-right: 1px solid #000;
}
#appSelection,
#appPrint {
  border-bottom: 1px solid #000;
  padding: 8px;
}
#functional {
  display: grid;
  grid-template-columns: 0.2fr 0.4fr 0.4fr 0.4fr 0.2fr 0.4fr 0.2fr;
  margin-top: 6vh;
}
</style>
