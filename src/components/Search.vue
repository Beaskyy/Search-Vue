<template>
  <div>
    <form>
      <div class="box">
        <div class="search">
          <div class="search-icon">
            <i class="fa-solid fa-magnifying-glass"></i>
          </div>
          <div>
            <input
              class="search-input"
              placeholder="Search Keyword"
              type="text"
            />
          </div>
        </div>
        <div class="location">
          <div class="icon">
            <i
              v-bind:class="['fa-solid fa-folder-open', show && 'active']"
              @click="a()"
            ></i>
            <!-- <input v-show="show" type="text" placeholder="Select Category" /> -->
            <select v-show="show">
              <option value="">Select Category</option>
              <option value="">option 1</option>
              <option value="">option 2</option>
              <option value="">option 3</option>
            </select>
          </div>
          <div class="icon">
            <i
              v-bind:class="['fa-solid fa-location-dot', location && 'active']"
              @click="b()"
            ></i>
            <!-- <input v-show="location" type="text" placeholder="Select Location" /> -->
            <select v-show="location">
              <option value="">Select Location</option>
              <option value="">option 1</option>
              <option value="">option 2</option>
              <option value="">option 3</option>
            </select>
          </div>
          <div class="icon">
            <i
              v-bind:class="[
                'fa-sharp fa-solid fa-location-crosshairs',
                range && 'active',
              ]"
              @click="c()"
            ></i>
            <div class="dropdown">
              <p
                class="dropdown-toggle"
                data-bs-toggle="dropdown"
                aria-expanded="false"
              >
                {{ distance }}km
              </p>
              <ul class="dropdown-menu text-center mt-3">
                <label for="customRange1" class="form-label"
                  >set distance for search</label
                >
                <input
                  type="range"
                  class="form-range"
                  min="0"
                  max="100"
                  v-model="distance"
                />
              </ul>
            </div>
          </div>
          <button class="search-button">Search</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      show: false,
      location: false,
      range: false,
      distance: null,
    };
  },
  methods: {
    a() {
      this.show = !this.show;
    },

    b() {
      this.location = !this.location;
    },
    c() {
      this.range = !this.range;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.box {
  display: flex;
  justify-content: center;
}

.search {
  display: flex;
}
.location {
  display: flex;
  flex-wrap: wrap;
}
.icon {
  display: flex;
  align-items: center;
  background-color: #ffffff;
  padding: 2px 15px;
  color: rgb(128, 128, 128);
  cursor: pointer;
}

.search-icon {
  display: flex;
  align-items: center;
  background-color: #ffffff;
  color: #222;
  padding: 10px 20px;
  border-radius: 5px 0 0 5px;
}

input::placeholder {
  font-family: "Montserrat", sans-serif;
  font-size: 15px;
}

.search-input {
  border: none;
  background-color: #ffffff;
  height: 50px;
  box-shadow: none;
  outline: none;
  padding: 5px;
  width: 200px;
}

input[type="text"] {
  font-family: "Montserrat", sans-serif;
  font-size: 15px;
  color: #444;
}
.icon input {
  border: none;
  outline: none;
  height: 40px;
  width: 120px;
}
.active {
  color: #333;
}
.search-button {
  font-family: "Montserrat", sans-serif !important;
  font-size: 15px;
  border-radius: 5px;
  border: none;
  height: 50px;
  width: 150px;
  margin: 0 0 0 -4px;
  background-color: #2d48c3;
  border-color: #2d48c3;
  color: #ffffff;
  fill: #ffffff;
  cursor: pointer;
}

select {
  padding: 10px;
  border: none;
}

.dropdown-menu {
  width: 200px;
}
.dropdown-toggle {
  padding: 0 10px;
  margin: 2px;
}

input[type="range"] {
  width: 90%;
}

@media screen and (max-width: 600px) {
  .box {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .search-input {
    width: 400px;
    border-radius: 10px;
    margin-left: -8px;
  }
  .icon {
    display: flex;
    margin: 6px 4px;
    border-radius: 5px;
    padding: 10px 20px;
  }

  .search-button {
    margin: 6px;
  }
}

@media screen and (max-width: 500px) {
  .search-input {
    width: 300px;
  }
}
</style>
