<template>
  <div class="w-full h-full">
    <!-- Normal Smile -->
    <svg
      v-if="type == 'normal-smile'"
      width="30"
      height="18"
      viewBox="0 0 30 18"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M24.5 8C18.8 11.4 8.7 7.7 4 2"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <!-- Normal Thin -->
    <svg
      v-if="type == 'normal-thin'"
      width="30"
      height="16"
      viewBox="0 0 30 16"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M25.5 4.5C21.1 7.1 14.1 5.5 9 2"
        stroke="#FEE4BF"
        stroke-width="2.4681"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <!-- Eat -->
    <svg
      v-if="type == 'eat'"
      width="30"
      height="17"
      viewBox="0 0 30 17"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M27.6999 6.2C24.0999 8.3 18.8999 7.7 14.3999 5.5"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
      <path
        d="M14.9 2C14.9 2 14.9 6.4 10 8.2"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <!-- Open Mouth -->
    <svg
      v-if="type == 'open-mouth'"
      width="30"
      height="20"
      viewBox="0 0 30 20"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M25.9585 9.25018C26.0585 10.8502 24.8584 13.6502 22.6584 15.6502C11.3584 8.75017 6.25844 12.3502 6.25844 12.3502C2.25844 6.25019 3.15845 -2.04982 12.8584 4.25018C19.6585 8.55018 23.7585 9.25018 25.9585 9.25018Z"
        fill="#423232"
      />
      <path
        d="M22.6583 15.6502C20.2583 17.7502 16.6583 19.0502 11.7583 17.0502C9.4583 16.1502 7.6583 14.3502 6.2583 12.3502C6.2583 12.3502 11.3583 8.7502 22.6583 15.6502Z"
        fill="#FE9DAB"
      />
      <path
        d="M27.8583 8.85025C27.8583 8.85025 23.6583 11.1502 12.8583 4.25024C-0.0416775 -4.04976 2.55831 13.3502 11.6583 17.0502C21.1583 20.9502 26.0583 12.4502 25.9583 9.25024"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
      <path
        d="M6.2583 12.3502C6.2583 12.3502 11.3583 8.7502 22.6583 15.6502"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <!-- Open Touth -->
    <svg
      v-if="type == 'open-touth'"
      width="30"
      height="20"
      viewBox="0 0 30 20"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M25.997 9.21801C26.097 12.518 21.197 20.918 11.697 17.018C2.59699 13.318 -0.102994 -4.08199 12.897 4.21801C19.697 8.51801 23.797 9.21801 25.997 9.21801Z"
        fill="white"
      />
      <path
        d="M27.8969 8.81802C27.8969 8.81802 23.6969 11.118 12.8969 4.21801C-0.00310326 -4.08199 2.59688 13.318 11.6969 17.018C21.1969 20.918 26.0969 12.418 25.9969 9.21801"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
      <path
        d="M4.09668 6.71802C4.09668 6.71802 10.8967 11.218 12.8967 10.818C14.9967 10.518 14.6967 13.418 24.1967 13.718"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <!-- Sad -->
    <svg
      v-if="type == 'sad'"
      width="30"
      height="16"
      viewBox="0 0 30 16"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M27.5 9.08889C27.5 9.08889 23.5 4.38889 7 9.08889"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <!-- Angry -->
    <svg
      v-if="type == 'angry'"
      width="33"
      height="18"
      viewBox="0 0 33 18"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M28.4092 7.22608C28.2092 8.92608 28.1092 10.1261 27.8092 11.1261C26.6092 16.4261 24.2092 13.8261 19.8092 13.9261C14.3092 14.0261 4.90922 19.3261 2.90922 12.2261C2.50922 10.9261 2.30923 9.72609 2.20923 8.62609C1.20923 -1.37391 11.0092 1.92608 20.8092 5.72608C24.6092 7.32608 27.0092 7.42608 28.4092 7.22608Z"
        fill="white"
      />
      <path
        d="M27.909 11.1261L25.209 10.826"
        :stroke="color"
        stroke-width="2.6265"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
      <path
        d="M30.9093 5.7261C30.9093 5.7261 29.5093 9.22611 20.8093 5.82611C9.80933 1.52611 -1.29067 -1.97389 2.90933 12.3261C5.00933 19.3261 14.3093 14.1261 19.8093 14.0261C25.0093 13.9261 27.4093 17.5261 28.4093 7.32611"
        :stroke="color"
        stroke-width="2.6265"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
      <path
        d="M2.20898 8.62603C3.20898 8.82603 8.80898 6.82602 10.109 8.72602C11.409 10.626 13.009 8.92602 13.809 9.22602C14.609 9.52602 18.209 10.026 18.209 10.026"
        :stroke="color"
        stroke-width="2.6265"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <!-- Cute -->
    <svg
      v-if="type == 'cute'"
      width="34"
      height="19"
      viewBox="0 0 34 19"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M28.1 2.40592C28.1 2.40592 30.7 1.00592 32.1 3.40592C33.5 5.80592 30.1 8.50591 30.1 8.50591C30.1 8.50591 33.9 11.3059 31.3 14.8059C29.2 17.6059 26 17.4059 26 17.4059"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <!-- Hate -->
    <svg
      v-if="type == 'hate'"
      width="33"
      height="16"
      viewBox="0 0 33 16"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M30.8 7.65118C30.8 7.65118 18.1 1.75118 12 4.95118"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    <!-- Smiliey -->
    <svg
      v-if="type == 'smiliey'"
      width="31"
      height="16"
      viewBox="0 0 31 16"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M28.8 6.70001C26.3 7.80001 25.1 5.6 21.2 7.5C18.4 8.8 16.9 9.20001 13.5 7.20001C11.3 5.80001 8.6 7.8 6 4"
        :stroke="color"
        stroke-width="3"
        stroke-miterlimit="10"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
  </div>
</template>
<script>
export default {
  name: 'MouthType',
  props: {
    color: { type: String, default: '#423232' },
    type: { type: String, default: 'open-mouth' },
  },
}
</script>
<style>
svg {
  width: 100%;
  height: 100%;
}
</style>
