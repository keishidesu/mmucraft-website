<template>
  <div class="card bg-dark">
    <div class="card-header" id="FAQ-header-<%= id %>">
      <h2>
        <button class="btn btn-light text-decoration-none text-left" type="button" data-toggle="collapse" data-target="#FAQ-collapse-<%= id %>" aria-expanded="true" aria-controls="FAQ-collapse-<%= id %>">
          <!-- <%- item.question %> -->
        </button>
      </h2>
    </div>
    <div id="FAQ-collapse-<%= id %>" class="collapse" aria-labelledby="FAQ-header-<%= id %>" data-parent="#accordionFAQ">
      <div class="card-body gl-bg-black-10">
        <!-- <%- item.answer %> -->
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>