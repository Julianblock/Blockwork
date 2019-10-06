<template>
    <div class="row">
        <div class="home-post">
            <input class="home-post-input" placeholder="Post something: " v-model="posting" type="text" />
            <input type="file" @change="previewImage" accept="image/*" />
            <button>Post</button>
        </div>
        <h1>Post Preview: </h1>
        <div class="home-news-preview" :style="{ 'background-image': 'url(' + imageData + ')' }" >
            <p> {{ posting }} </p>
        </div>
    </div>
</template>

<script>
export default {
    data () { 
        return {
            posting: "",
            imageData: ""  // we will store base64 format of image in this string
        }
    },
    methods: {
        previewImage: function(event) {
            // Reference to the DOM input element
            var input = event.target;
            // Ensure that you have a file before attempting to read it
            if (input.files && input.files[0]) {
                // create a new FileReader to read this image and convert to base64 format
                var reader = new FileReader();
                // Define a callback function to run, when FileReader finishes its job
                reader.onload = (e) => {
                    // Note: arrow function used here, so that "this.imageData" refers to the imageData of Vue component
                    // Read image as base64 and set to imageData
                    this.imageData = e.target.result;
                }
                // Start the reader job - read file as a data url (base64 format)
                reader.readAsDataURL(input.files[0]);
            }
        }
    }
}
</script>

<style lang="scss" scoped>
.row {
    display: flex;
    flex-flow: column;
    width: 100%;
}
.home-news-preview {
    width: 100%;
    box-shadow: 0px 0px 15px grey;
    height: 400px;
    background-size: cover;
    padding: 18px;

    p {
        color: #fff;
        text-shadow: 0px 0px 7px #000;
        font-size: 18px;
    }
}
</style>