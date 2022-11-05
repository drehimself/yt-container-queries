<script setup></script>

<template>
  <div class="weather-widget">
    <div class="current-weather-container">
      <div class="location-container">
        <div class="location-city">Toronto</div>
        <div class="location-country">Canada</div>
      </div>
      <div>
        <img
          src="../assets/sunny.svg"
          alt="sunny"
          class="current-weather-icon"
        />
      </div>
      <div>
        <div class="current-temperature">23 &#8451;</div>
        <div class="current-description">Partly Cloudy</div>
      </div>
    </div>

    <div class="weekly-weather-container">
      <div class="day-container">
        <div class="day">Sat</div>
        <div class="day-icon">
          <img src="../assets/sunny.svg" class="day-icon" alt="weather icon" />
        </div>
        <div class="temperature-container">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container">
        <div class="day">Sun</div>
        <div class="day-icon">
          <img src="../assets/cloudy.svg" class="day-icon" alt="weather icon" />
        </div>
        <div class="temperature-container">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container">
        <div class="day">Mon</div>
        <div class="day-icon">
          <img src="../assets/rain.svg" class="day-icon" alt="weather icon" />
        </div>
        <div class="temperature-container">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container">
        <div class="day">Tue</div>
        <div class="day-icon">
          <img
            src="../assets/partly-cloudy.svg"
            class="day-icon"
            alt="weather icon"
          />
        </div>
        <div class="temperature-container">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container">
        <div class="day">Wed</div>
        <div class="day-icon">
          <img src="../assets/sunny.svg" class="day-icon" alt="weather icon" />
        </div>
        <div class="temperature-container">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container">
        <div class="day">Thu</div>
        <div class="day-icon">
          <img src="../assets/sunny.svg" class="day-icon" alt="weather icon" />
        </div>
        <div class="temperature-container">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.weather-widget {
  font-family: sans-serif;
  background: #1d567c;
  color: white;
  border-radius: 8px;
  line-height: 1.4;
}

.current-weather-container {
  display: flex;
  gap: 10px;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  padding: 14px 10px;
  text-align: center;
}

.location-container {
  text-transform: uppercase;
  font-weight: bold;
}

.current-temperature {
  font-size: 28px;
}

.current-weather-icon {
  width: 64px;
}

.weekly-weather-container {
  display: flex;
  flex-direction: column;
  gap: 4px;
  justify-content: space-around;
  text-align: center;
  margin: 10px 0;
}

.day-container {
  font-size: 14px;
  padding: 14px 10px;
}

.day {
  text-transform: uppercase;
}

.day-icon {
  width: 28px;
  padding: 2px 0;
  margin: auto;
}

@media (min-width: 400px) {
  .current-weather-container {
    flex-direction: row;
    gap: 0;
  }

  .weekly-weather-container {
    flex-direction: row;
  }
}
</style>
