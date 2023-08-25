<template>
  <ul class="people-list">
    <TheCard
      v-for="(person, index) in people"
      :key="index"
      :imgSrc="person.image"
      :name="person.name"
      :role="person.role"
      :description="person.description"
      :path="person.link"
    />
  </ul>
</template>

<script>
import TheCard from "./TheCard.vue";

// As json file
import peopleList from "../assets/peopleList.json";

// As a variable
// const peopleList = [
//   {
//     id: 1,
//     image:
//       "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSMoW_B9Rgh-_-ovMV2XU6NpH5l9RXQgY3mLQ&usqp=CAU",
//     name: "Joey",
//     role: "Wannabe Actor",
//     description:
//       "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
//     link: ""
//   },
//   {
//     id: 2,
//     image:
//       "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRgZNuc_b9iZjABVZYiVresqbux3phU1cFQwg&usqp=CAU",
//     name: "Chandler",
//     role: "Transponster",
//     description:
//       "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
//     link: ""
//   },
//   {
//     id: 3,
//     image:
//       "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS8gzBd5ATFOceMISo19e1JSuM-g-A1oQcKLw&usqp=CAU",
//     name: "Ross",
//     role: "Dinosaurs",
//     description:
//       "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
//     link: ""
//   },
//   {
//     id: 4,
//     image:
//       "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS4OW6g80m1dlwlRXdPzmzAK04ax4zebEttHQ&usqp=CAU",
//     name: "Rachel",
//     role: "Compulsive Buyer",
//     description:
//       "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
//     link: ""
//   },
//   {
//     id: 5,
//     image:
//       "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTwuwK0fQYykYVLRxa7u0g7UwT3geUH4C8p1w&usqp=CAU",
//     name: "Monica",
//     role: "Chef",
//     description:
//       "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
//     link: ""
//   },
//   {
//     id: 6,
//     image:
//       "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQzkpi_YTYLeUKobJjUFYzM_tHNN1M6a8iEqQ&usqp=CAU",
//     name: "Phoebe",
//     role: "Singer",
//     description:
//       "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
//     link: ""
//   }
// ];

export default {
  components: { TheCard },
  data() {
    return {
      people: peopleList
    };
  }
};
</script>

<style scoped>
.people-list {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 60px;
  list-style: none;
  padding: 0;
  margin: 0;
}
</style>
