<template>
  <Modal
    data-testid="preview-resource-modal"
    :show="show"
    @close-via-escape="$emit('close')"
    role="alertdialog"
    maxWidth="2xl"
  >
      <slot>
        <ModalHeader 
          class="flex items-center bg-gray-100"
        >
           {{ data.title }}
        </ModalHeader>
        <ModalContent 
          class="px-8 bg-gray-100"
        >
       {{ data.message }}
        </ModalContent>
      </slot>
      <ModalFooter>
        <div 
          class="ml-auto"
        >
          <span class="mr-3" />
          <LoadingButton
            @click.prevent="$emit('close')"
            ref="confirmButton"
            dusk="confirm-preview-button"
          >
            {{ __('Close') }}
          </LoadingButton>
        </div>
      </ModalFooter>
  </Modal>
</template>

<script>
export default {
  props: {
    data: {type: Object}
  }
}
</script>