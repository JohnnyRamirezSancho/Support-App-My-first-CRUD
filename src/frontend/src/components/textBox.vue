<script setup>

window.onload = function formDate() {
  let today = new Date();

  let day = today.getDate();
  let month = today.getMonth() + 1;
  let year = today.getFullYear();

  day = ('0' + day).slice(-2);
  month = ('0' + month).slice(-2);

  let printDate = `${day}/${month}/${year}`

  document.getElementById("date").innerHTML = printDate
};

    function deleteButton(){
        document.getElementById("issueTemplate").remove("issueTemplate");
    }


</script>

<template>
    <div id="issueTemplate" class="accordion w-75 mx-auto">
        <div class="accordion-item">
            <div class="accordion-header" id="issueTemplateHeader">
                <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#issueTextBox" aria-expanded="true" aria-controls="issueTextBox">
                    <p id="date" class="fs-4"></p>
                    <p id="reference" class="ms-3 fw-bold fs-4">Incidence Name</p>
                </button>
            </div>

            <div id="issueTextBox" class="accordion-collapse collapse show" aria-labelledby="issueTemplateHeader" data-bs-parent="#issueTemplate">
                <div class="accordion-body">
                    <div id="userName" class="fs-5 fw-bold">
                        Sent by: <p id="userNameInput"></p>
                    </div>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. In autem voluptates nihil rem reiciendis blanditiis fugiat, asperiores quasi, veritatis ullam recusandae repudiandae eveniet quia sequi fugit? Rem laudantium ipsa aperiam.
                </div>
                <div class="d-md-flex justify-content-md-end">
                    <button id="deleteButton" class="rounded border border-0 bg-danger mx-3 my-2 btn btn-lg" @click="deleteButton()">Delete</button>
                    <router-link to="/ModifyIncident">
                        <button id="modifyButton" class="rounded border border-0 bg-info mx-3 my-2 btn btn-lg">Modify</button>
                    </router-link>  
                </div>
            </div>
        </div>
    </div>

</template>

<style lang="scss" scoped>

</style>