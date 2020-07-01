<template>
  <b-col cols="12" lg="8" class="mt-3">
    <div class="card rounded gl-bg-white-10 shadow">
      <div class="card-header mc-title font-weight-bolder" style="color:red; font-size:1.5rem">
        Announcement
      </div>
      <div class="card-body">
        <div class="row">
          <div id="spy" class="col-sm-2">
            <ul class="nav nav-pills flex-column">
              <!--Repeating components-->
              <li class="nav-item">
                <a class="nav-link text-white active" href="#announcement1">
                  1/10/2019
                </a>
              </li>
            </ul>
          </div>
          <div class="col-sm-10 text-white" data-spy="scroll" data-target="#spy" style="position: relative; height: 350px; overflow: auto;">
            <!--Repeating components-->
            <div id="announcement1" class="mt-2">
              <h4 class="text-primary">
                1/10/2019
              </h4>
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
              </p>
              <p class="blockquote-footer text-white gl-opac-80">
                Dev1
              </p>
              <hr>
            </div>
          </div>
        </div>
      </div>
    </div>
  </b-col>
</template>

<script>
export default {

}
</script>

<style>

</style>
