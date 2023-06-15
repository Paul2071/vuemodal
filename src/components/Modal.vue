<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale: theme === 'sale'}">

            <slot>default content -- something gone wrong!</slot>

            <div class="actions">
              <slot name="citadel"></slot>
            </div>
            
            
        </div>
    </div>
</template>

<script>

export default {
  props: [ "theme"],
  methods: {
    closeModal() {
        this.$emit('closemodal')
    }
  }
}

</script>

<style>
  .modal {
    width: 400px;
    padding: 20px;
    margin: 200px auto;
    background: white;
    border-radius: 10px;
  }
  .backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
  }
  .modal.sale {
    background: crimson;
    color: white;
  }


</style>