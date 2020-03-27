<template>
  <div>
    <PhotoCluster
      imagefile1="https://i.ytimg.com/vi/yaY0lHcynpU/hqdefault.jpg"
      imagedescription1="This is some text describing the project. It was a great project that is very good and has lots of excellent things to offer"
      :uselink="true"
    />
  </div>
</template>

<script>
import PhotoCluster from "../components/PhotoCluster";

export default {
  components: { PhotoCluster }
};
</script>

<style lang="scss" scoped></style>
