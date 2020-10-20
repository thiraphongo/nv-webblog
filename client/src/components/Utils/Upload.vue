<template>
<div>
<!-- <back-header /> -->
<h1>Upload Material:</h1>
<form enctype="multipart/form-data" novalidate>
<div class="dropbox">

<input type="file" multiple :name="uploadFieldName"
:disabled="isSaving" @change="filesChange($event.target.name,
$event.target.files); fileCount = $event.target.files.length"
accept="image/*" class="input-file">
<!-- <p v-if="isInitial || isSuccess"> -->
<p v-if="isInitial">
Drag your file(s) here to begin<br> or click to browse
</p>
<p v-if="isSaving">
Uploading {{ fileCount }} files...
</p>
<p v-if="isSuccess">
Upload Successful.
</p>
</div>
</form>
</div>
</template>

<style scoped>
.dropbox {
outline: 2px dashed grey; /* the dash box */
outline-offset: -10px;
background:lemonchiffon;
color: dimgray;
padding: 10px 10px;
min-height: 200px; /* minimum height */
position: relative;
cursor: pointer;
}
.input-file {
opacity: 0; /* invisible but it's there! */
width: 100%;
height: 200px;
position: absolute;
cursor: pointer;
}
.dropbox:hover {
background:khaki; /* when mouse over to the drop zone, change color
*/
}
.dropbox p {
font-size: 1.2em;
text-align: center;
padding: 50px 0;
}

ul.pictures {
list-style: none;
padding: 0;
margin: 0;
float: left;
padding-top: 10px;
padding-bottom: 10px;
}
ul.pictures li {
float: left;
}
ul.pictures li img {
max-width: 180px;
margin-right: 20px;
}
.clearfix {
clear: both;
}
</style>
