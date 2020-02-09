<template>
  <div class="profile">
    <div class="basic_details">
      <img src="../assets/profile.jpg" alt="profile" />
      <div class="container">
        <div>
          <div class="name" v-text="name"></div>
          <div class="designation" v-text="designation"></div>
        </div>
        <div>
          <div>Phone:</div>
          <div class="phone" v-text="phone"></div>
        </div>
        <div>
          <div>Email:</div>
          <div class="email" v-text="email"></div>
        </div>
      </div>
    </div>
    <div class="about">
      <div>About:</div>
      <p class="description" v-text="description"></p>
    </div>
  </div>
</template>
<script>
export default {
  name: "Profile",
  props: {
    imageLocation: String,
    name: String,
    designation: String,
    description: String,
    phone: String,
    email: String
  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Montserrat");
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Montserrat", sans-serif;
  color: #fff;
}
@media only screen and (min-width: 320px) {
  .profile {
    width: 100%;
    height: 100%;
    margin: 0.7em auto;
    padding: 5px;
    background: #2e4a62;
    border-radius: 4px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    line-height: 20px;
  }
  img {
    width: 250px;
    height: 250px;
    margin: 5px;
    object-fit: cover;
  }
  .container,
  .about {
    text-align: left;
    width: 250px;
    margin: 0px auto;
  }
  .container > div,
  .about {
    margin-top: 10px;
  }
  .designation,
  .description,
  .phone,
  .email {
    font-size: 0.8em;
    color: #94ff92;
  }
  .container > div:nth-child(1) > div:nth-child(1),
  .container > div:nth-child(2) > div:nth-child(1),
  .container > div:nth-child(3) > div:nth-child(1),
  .container > div:nth-child(4) > div:nth-child(1),
  .about > div {
    font-size: 1em;
    font-weight: bold;
  }
  .description {
    color: #fffcfc;
    text-align: justify;
  }
}
@media only screen and (min-width: 768px) {
  .profile {
    width: 80%;
    height: 100%;
    margin: 1em auto;
    padding: 35px;
    background: #2e4a62;
    border-radius: 4px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    line-height: 20px;
  }
  .basic_details {
    display: flex;
    align-items: flex-start;
  }
  .about {
    width: 100%;
  }
  img {
    width: 250px;
    height: 250px;
    margin: 5px;
    object-fit: cover;
  }
  .container {
    text-align: left;
    width: 100%;
    padding-left: 5px;
  }
  .container > div,
  .about {
    margin-top: 10px;
  }
  .designation,
  .description,
  .phone,
  .email {
    font-size: 1em;
    color: #94ff92;
  }
  .container > div:nth-child(1) > div:nth-child(1),
  .container > div:nth-child(2) > div:nth-child(1),
  .container > div:nth-child(3) > div:nth-child(1),
  .container > div:nth-child(4) > div:nth-child(1),
  .about > div {
    font-size: 1em;
    font-weight: bold;
  }
  .description {
    color: #fffcfc;
    text-align: justify;
  }
}
</style>
