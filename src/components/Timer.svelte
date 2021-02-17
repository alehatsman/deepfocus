<script type="ts">
  import Circle from './Circle.svelte'
  export let time: number
  export let progress: number

  const formatTime = (v) => {
    return v < 10 ? `0${v}` : `${v}` 
  }

  const format = (time) => {
    const mins = Math.floor(time / 60)
    const seconds = time % 60
    return `${formatTime(mins)}:${formatTime(seconds)}`
  }
</script>

<div class="timer">
  <!--
  <div class="timer__progress">
    <Circle 
      radius={250} 
      stroke={10} 
      progress={progress}
    />
  </div>
  -->
  <span class="timer__time">
    {format(time)}
  </span>
</div>

<style>
  .timer {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    /*
    width: 500px;
    height: 500px;
    */
  }

  .timer__progress {
    position: absolute;
  }

  .timer__time {
    font-family: Source Code Pro, monospace;
    font-style: normal;
    font-weight: 200;
    font-size: 170px;
    line-height: 132px;
    display: flex;
    align-items: center;
    text-align: center;
    letter-spacing: -10px;
    color: var(--font-color);
    user-select: none;
  }
</style>
