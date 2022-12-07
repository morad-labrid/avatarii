<!-- Please remove this file from your project -->
<template>
  <div class="flex justify-between">
    <!-- Left side (settings) -->
    <section class="bg-white p-4 rounded-2xl w-72">
      <!-- switch buttons -->
      <div
        class="flex items-center justify-between space-x-4 p-2 bg-orange-200/60 rounded-xl"
      >
        <span
          class="cursor-pointer bg-white p-2 rounded-lg"
          @click="changeInterface('left')"
        >
          <arrow-left />
        </span>
        <p class="text-sky-800/90 font-bold">
          {{
            avatar[index].title[0].toUpperCase() + avatar[index].title.slice(1)
          }}
        </p>
        <span
          class="cursor-pointer bg-white p-2 rounded-lg"
          @click="changeInterface('right')"
        >
          <arrow-right class="cursor-pointer bg-white" />
        </span>
      </div>
      <!-- settings -->
      <div>
        <div
          class="grid grid-cols-4 p-2 gap-2 m-auto mt-2 h-48 overflow-y-auto"
        >
          <div
            :is="avatar[index].component"
            v-for="(style, i) in avatar[index].style"
            :key="'element' + i"
            :class="
              style == myavatar[avatar[index].title].style
                ? 'ring ring-offset-2 flex bg-gray-200 rounded-full w-12 h-12 cursor-pointer transition-all'
                : 'flex bg-gray-200 rounded-full w-12 h-12 cursor-pointer'
            "
            :type="style"
            :color="myavatar[avatar[index].title].color"
            classname="classname"
            @click.native="setHairStyle(avatar[index].title, 'style', style)"
          ></div>
        </div>
        <div class="h-5 w-full"></div>
        <div class="flex flex-wrap justify-center px-2">
          <div
            v-for="(color, i) in avatar[index].color"
            :key="'color' + i"
            :style="'background-color:' + color"
            :class="
              color == myavatar[avatar[index].title].color
                ? 'ring ring-offset-2 w-4 h-4 rounded-full mx-2 my-1 cursor-pointer transition-all'
                : 'w-4 h-4 rounded-full mx-2 my-1 cursor-pointer'
            "
            @click="setHairStyle(avatar[index].title, 'color', color)"
          ></div>
        </div>
      </div>
    </section>
    <!-- Right side (view) -->
    <section
      class="relative h-fit bg-white p-4 pr-16 pb-24 -rotate-6 -right-14 top-6 rounded-2xl"
    >
      <div
        class="relative w-40 h-40 rounded-xl -mb-2 overflow-hidden"
        :style="'background-color:' + myavatar.background.color"
      >
        <face-type
          :color="myavatar.face.color"
          :type="myavatar.face.style"
          class="absolute face"
        />
        <eyes-type
          :eyes="myavatar.eyes.color"
          :eyebrows="myavatar.eyebrows.color"
          :type="myavatar.eyes.style"
          class="absolute eyes"
        />
        <mouth-type :type="myavatar.mouth.style" class="absolute mouth" />
        <outfit-style
          :type="myavatar.outfit.style"
          :color="myavatar.outfit.color"
          class="absolute outfit"
        />
        <hair-type
          :color="myavatar.hair.color"
          :type="myavatar.hair.style"
          class="absolute hair"
        />
        <!-- <accessory-type
          :type="myavatar.accessory.style"
          class="absolute accessory"
        /> -->
      </div>
    </section>
  </div>
</template>

<script>
import ArrowLeft from '@/components/layouts/arrow-left.vue'
import ArrowRight from '@/components/layouts/arrow-right.vue'
import FaceType from './layouts/avatar/face/FaceType.vue'
import EyesType from './layouts/avatar/eyes/EyesType.vue'
import MouthType from './layouts/avatar/mouth/MouthType.vue'
import HairType from './layouts/avatar/hair/HairType.vue'
import OutfitStyle from './layouts/avatar/outfit/OutfitStyle.vue'
// import AccessoryType from './layouts/avatar/accessory/AccessoryType.vue'
import backgroundColor from './layouts/avatar/background/BackgroundColor.vue'
export default {
  name: 'AvatarComponent',
  components: {
    ArrowLeft,
    ArrowRight,
    FaceType,
    EyesType,
    MouthType,
    HairType,
    OutfitStyle,
    backgroundColor,
    // AccessoryType,
  },
  data() {
    return {
      index: 0,
      myavatar: {
        face: { style: 'face-01', color: '#DEB3A3' },
        hair: { style: 'style-01', color: '#4B301C' },
        eyes: { style: 'normal', color: '#280000' },
        eyebrows: { color: '#4B301C' },
        mouth: { style: 'normal-smile' },
        outfit: { style: 'outfit-01', color: '#f4acb7' },
        background: { style: 'background-01', color: '#B5E2DC' },
        // accessory: { style: 'accessory-01' },
      },
      avatar: [
        {
          title: 'face',
          component: 'face-type',
          style: ['face-01'],
          color: [
            '#FADCD1',
            '#F8D9CE',
            '#F6D7CB',
            '#EDC9BC',
            '#DEB3A3',
            '#C89583',
            '#D9A392',
            '#B78276',
            '#9C6458',
            '#753D39',
            '#5F2828',
            '#501F1F',
          ],
        },
        {
          title: 'hair',
          component: 'hair-type',
          style: [
            'style-01',
            'style-02',
            'style-03',
            'style-04',
            'style-05',
            'style-06',
            'style-07',
            'style-08',
            'style-09',
            'style-10',
            'style-11',
            'style-12',
            'style-13',
            'style-14',
            'style-15',
            'style-16',
            'style-17',
            'style-18',
            'style-19',
            'style-20',
            'style-21',
            'style-22',
            'style-23',
          ],
          color: [
            '#E3E0D9',
            '#F6C870',
            '#FCAC15',
            '#CE7230',
            '#901DAC',
            '#865028',
            '#4B301C',
            '#150C0C',
          ],
        },
        {
          title: 'mouth',
          component: 'mouth-type',
          style: [
            'normal-smile',
            'normal-thin',
            'eat',
            'open-mouth',
            'open-touth',
            'sad',
            'angry',
            'cute',
            'hate',
            'smiliey',
          ],
          color: ['#423232'],
        },
        {
          title: 'outfit',
          component: 'outfit-style',
          style: [
            'outfit-01',
            'outfit-02',
            'outfit-03',
            'outfit-04',
            'outfit-05',
            'outfit-06',
            'outfit-07',
            'outfit-08',
            'outfit-09',
            'outfit-10',
          ],
          color: [
            '#f4acb7',
            '#ff686b',
            '#f4845f',
            '#fdc921',
            '#faedcd',
            '#84a98c',
            '#87986a',
            '#5fa8d3',
            '#9c89b8',
            '#463f3a',
            '#bfc0c0',
          ],
        },
        {
          title: 'eyes',
          component: 'eyes-type',
          style: ['thin', 'closed', 'cynic', 'sad', 'angry', 'normal'],
          color: [
            '#8BB5DB',
            '#4079C0',
            '#B3B9B9',
            '#8E9796',
            '#75899D',
            '#89947C',
            '#6E9D4C',
            '#AA6925',
            '#55230C',
            '#3F0D0A',
            '#280000',
          ],
        },
        {
          title: 'eyebrows',
          component: 'eyes-type',
          style: [],
          color: [
            '#E3E0D9',
            '#F6C870',
            '#FCAC15',
            '#CE7230',
            '#901DAC',
            '#865028',
            '#4B301C',
            '#150C0C',
          ],
        },
        {
          title: 'background',
          component: 'background-color',
          style: ['background-01'],
          color: [
            '#fbc4ab',
            '#ffbf69',
            '#e6ccb2',
            '#ffe169',
            '#B5E2DC',
            '#e5e5e5',
            '#90e0ef',
            '#669bbc',
            '#a2d2ff',
            '#dec0f1',
            '#bfd8bd',
            '#B5E2C9',
            '#F4DA92',
            '#fff3b0',
            '#353535',
            '#e5e5e5',
          ],
        },
        // {
        //   title: 'accessory',
        //   component: 'accessory-type',
        //   style: [
        //     'accessory-01',
        //     'accessory-02',
        //     'accessory-03',
        //     'accessory-04',
        //     'accessory-05',
        //   ],
        //   color: ['#fbc4ab', '#ffbf69', '#e6ccb2'],
        // },
      ],
    }
  },
  methods: {
    setHairStyle(body, key, value) {
      // Hair parameters
      if (body == 'hair' && key === 'style') this.myavatar.hair.style = value
      if (body == 'hair' && key === 'color') this.myavatar.hair.color = value
      // Mouth parameters
      if (body == 'mouth' && key === 'style') this.myavatar.mouth.style = value
      // Outfit parameters
      if (body == 'outfit' && key === 'style')
        this.myavatar.outfit.style = value
      if (body == 'outfit' && key === 'color')
        this.myavatar.outfit.color = value
      // Face parameters
      if (body == 'face' && key === 'style') this.myavatar.face.style = value
      if (body == 'face' && key === 'color') this.myavatar.face.color = value
      // Eyes parameters
      if (body == 'eyes' && key === 'style') this.myavatar.eyes.style = value
      if (body == 'eyes' && key === 'color') this.myavatar.eyes.color = value
      // eyebrows parameters
      if (body == 'eyebrows' && key === 'color')
        this.myavatar.eyebrows.color = value
      // Background color
      if (body == 'background' && key === 'color')
        this.myavatar.background.color = value
      // Accessory
      if (body == 'accessory' && key === 'style')
        this.myavatar.accessory.style = value
    },
    changeInterface(direction) {
      if (direction == 'left' && this.index > 0) this.index--
      if (direction == 'right' && this.index + 1 < this.avatar.length)
        this.index++
    },
  },
}
</script>
<style>
.absolute {
  transform: translate(-50%, -50%);
}
.outfit {
  bottom: -57%;
  left: 55%;
  width: 70%;
  height: 70%;
}
.face {
  bottom: -22%;
  left: 50%;
  width: 60%;
  height: 60%;
}
.hair {
  bottom: -12.8%;
  left: 52.8%;
  width: 61%;
  height: 61%;
}
.eyes {
  bottom: 32%;
  left: 61.5%;
  width: 18%;
  height: 18%;
}
.mouth {
  bottom: 30%;
  left: 58%;
  width: 8%;
  height: 8%;
}
.accessory {
  top: 61%;
  left: 56.7%;
  width: 31%;
  height: 28%;
}

/* scrollbar */
/* width */
::-webkit-scrollbar {
  width: 8px;
}

/* Track */
::-webkit-scrollbar-track {
  /* box-shadow: inset 0 0 5px grey; */
  /* border-radius: 10px; */
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: rgb(7 89 133);
  border-radius: 10px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:active {
  background: rgb(11, 133, 198);
  color: #4e4e4e;
}
</style>
