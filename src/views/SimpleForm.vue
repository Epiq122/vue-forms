<script>
import { ref } from 'vue';
export default {
  setup() {
    const categories = ref([
      'sustainability',
      'nature',
      'animal welfare',
      'housing',
      'education',
      'food',
      'community',
    ]);
    const event = ref({
      category: '',
      title: '',
      description: '',
      location: '',
      pets: 1,
      extras: {
        catering: false,
        music: false,
      },
    });
    return {
      categories,
      event,
    };
  },
};
</script>

<template>
  <div>
    <h1>Create an Event</h1>
    <form>
      <label>Select a category</label>
      <select v-model="event.category">
        <option
          v-for="option in categories"
          :value="option"
          :key="option"
          :selected="option === event.category"
        >
          {{ option }}
        </option>
      </select>
      <h3>Name & describe your event</h3>
      <label>Title</label>
      <input
        type="text"
        v-model="event.title"
        placeholder="Title"
        class="field"
      />
      <label>Description</label>
      <input
        type="text"
        v-model="event.description"
        placeholder="Description"
        class="field"
      />
      <h3>Where is your event?</h3>
      <label>Location</label>
      <input
        type="text"
        v-model="event.location"
        placeholder="Location"
        class="field"
      />
      <h3>Are pets allowed?</h3>
      <div>
        <input type="radio" v-model="event.pets" :value="1" name="pets" />
        <label for="">Yes</label>
      </div>
      <div>
        <input type="radio" v-model="event.pets" :value="0" name="pets" />
        <label for="">No</label>
      </div>

      <h3>Extras</h3>
      <div>
        <input type="checkbox" v-model="event.extras.catering" class="field" />
        <label>Catering</label>
      </div>
      <div>
        <input type="checkbox" v-model="event.extras.music" class="field" />
        <label>Live Music</label>
      </div>
    </form>
  </div>
</template>

<style scoped></style>
