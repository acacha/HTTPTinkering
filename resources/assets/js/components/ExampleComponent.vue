<template>
    <div class="container">
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <div class="panel panel-default">
                    <div class="panel-heading">Example Component</div>

                    <div class="panel-body">
                        {{ user.name }} | {{ user.email}}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
      data() {
        return {
          user : {}
        }
      },
        mounted() {
          console.log('Component mounted.')
          // TODO header
          axios.get('api/user',{
            headers: { 'Authorization' : 'Bearer j69iqKrMYqS4TRfBqGdD2vfyGElazB2X2GKhON3gciDT4IOttshTD2nBZs0n' , 'HEADER1' : 'VALUE1'}
          }).then( response => {
           this.user = response.data
          }).catch(error => {
            console.log(error)
          })
        }
    }
</script>
