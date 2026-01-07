<script setup>
const deadPeople = [
  {
    name: 'Jesus Christ',
    age: '33',
    achievement: 'Founded Christianity, considered the Son of God by many.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/4/4a/Christ_in_the_Wilderness_-_Ivan_Kramskoy_-_Google_Art_Project.jpg'
  },
  {
    name: 'Adolf Hitler',
    age: '56',
    achievement: 'Leader of Nazi Germany, initiated World War II and the Holocaust.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/d/dc/Adolf_Hitler_cropped_restored.jpg'
  },
  {
    name: 'Pope John Paul II',
    age: '84',
    achievement: 'One of the most influential leaders of the 20th century, helped end communist rule in Europe.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/3/36/JohannesPaul2-1.jpg'
  },
  {
    name: 'Jeffrey Epstein',
    age: '66',
    achievement: 'Wealthy financier and convicted sex offender with high-profile connections.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/e/e0/Jeffrey_Epstein_2017_official_photo.jpg'
  },
  {
    name: 'Pablo Escobar',
    age: '44',
    achievement: 'Infamous Colombian drug lord and narco-terrorist, leader of the Medellín Cartel.',
    image: 'https://upload.wikimedia.org/wikipedia/commons/9/9a/Pablo_Escobar_Mugshot.jpg'
  }
]
</script>

<template>
  <div class="obituaries">
    <h1>In Memoriam</h1>
    <p class="subtitle">A sad page about those who have left us.</p>
    
    <div class="grid">
      <div v-for="person in deadPeople" :key="person.name" class="card">
        <img :src="person.image" :alt="person.name" class="portrait" />
        <div class="info">
          <h2>{{ person.name }}</h2>
          <p><strong>Age:</strong> {{ person.age }}</p>
          <p><strong>Biggest Achievement:</strong> {{ person.achievement }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.obituaries {
  padding: 2rem;
  color: #ccc;
  background: #1a1a1a;
  min-height: 100vh;
  font-family: serif;
}

h1 {
  text-align: center;
  font-size: 3rem;
  margin-bottom: 0.5rem;
}

.subtitle {
  text-align: center;
  font-style: italic;
  margin-bottom: 3rem;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.card {
  background: #2a2a2a;
  border: 1px solid #444;
  padding: 1rem;
  text-align: center;
  border-radius: 8px;
  transition: transform 0.3s;
}

.card:hover {
  transform: translateY(-5px);
  border-color: #666;
}

.portrait {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 4px;
  filter: grayscale(100%);
  margin-bottom: 1rem;
}

h2 {
  margin: 0.5rem 0;
  color: #fff;
}

p {
  margin: 0.5rem 0;
}
</style>
