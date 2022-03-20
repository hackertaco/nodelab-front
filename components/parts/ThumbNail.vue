<template>
  <div :class='showOthers' :style='styleObject'>
    <div v-if='showOthers' class='thumbnail-box'>
      <div :style="title.includes('LANG') ? {'font-size':'0.9vw'}:{'font-size':'1.35vw'}" class='thumbnail-title'>
        {{ title }}
      </div>
      <div class='mini-box'></div>
      <div :class='changeColor()' class='main-box'></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ThumNail',
  props: {
    styleObject: {
      type: Object,
      default: () => ({
        width: '138px',
        height: '138px',
        background: '#F2F2F2'
      })
    },
    showOthers: {
      type: Boolean,
      default: true
    },

    title: {
      type: String
    }

  },
  setup(props) {
    console.log(props.title)
    const changeColor = () => {
      const lists = ['frontend', 'backend', 'ios', 'android', 'devops', 'database', 'side project', 'programming language']
      const colors = ['blue', 'pink', 'grey', 'beige', 'skyblue', 'lime', 'mint', 'cyan']
      let color = 'cyan'
      for (let i = 0; i < colors.length; i++) {
        if (props.title.slice(0, 3).includes(lists[i].slice(0, 3).toUpperCase())) {
          color = colors[i]
        } else {
          continue
        }
      }
      return color
    }
    return {
      changeColor
    }
  }
}
</script>

<style lang='scss' scoped>
.thumbnail-box {
  position: relative;
  width: 100%;
  height: 100%;
}

.thumbnail-title {
  font-family: "Chakra Petch";
  font-weight: 600;
  font-size: $kor-26;
  text-transform: uppercase;
  color: $dark-191919;
  width: 68px;
  word-wrap: break-word;
  line-height: 26px;
  position: absolute;
  top: 25px;
  left: 15px;
}

.mini-box {
  width: 6px;
  height: 6px;
  background-color: $grey-3;
  position: absolute;
  top: 4px;
  right: 4px;
}

.main-box {
  position: absolute;
  width: 14px;
  height: 64px;
  //background-color: $blue;
  bottom: 0;
  right: 0;
}

.blue {
  background: $blue;
}

.pink {
  background: $pink;
}

.grey {
  background: $grey-3;
}

.beige {
  background: $beige;
}

.red {
  background: $red;
}

.cyan {
  background: $cyan;
}

.mint {
  background: $mint;
}

.lime {
  background: $lime;
}

.skyblue {
  background: $skyblue;
}

</style>
