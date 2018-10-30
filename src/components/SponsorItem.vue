<template>
    <div class="col-md-4">
        <div class="card mb-4 shadow-sm">
        <img class="card-img-top" v-bind:src="item.image" alt="Card image cap">
        <div class="card-body">
            <p class="card-text">{{item.description}}</p>
            <div class="progress">
                <div :class="'progress-bar ' + progressBarColor" role="progressbar" :style="'width: '+percentPledged+'%'" :aria-valuenow="percentPledged" aria-valuemin="0" aria-valuemax="100"></div>
            </div>
            <div class="d-flex justify-content-between align-items-center">
                <p>Funded: {{item.funded}}, Target: {{item.target}}, Percent {{ percentPledged}} </p>
            </div>
            <div class="d-flex justify-content-between align-items-center">
                <div class="btn-group">
                    <button type="button" @click="greet" class="btn btn-sm btn-outline-secondary">Support This</button>
                    <button type="button" class="btn btn-sm btn-outline-secondary">Edit</button>
                </div>
                <small class="text-muted">{{item.donors}} donors</small>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'SponsorItem',
  props: ['item'],
  computed: {
    percentPledged: function() {
        return Math.round((this.item.funded / this.item.target) * 100)
    },
    progressBarColor: function() {
        let current = this.percentPledged;
        if (current < 50) {
            return "bg-danger"
        } else if (current >= 50 && current < 75) {
            return "bg-warning"
        } else if (current >= 100) {
            return "bg-success"    
        } else {
            return "bg-info"
        }
      }
    }
}
</script>

<style scoped>
  .card-body .progress {
    margin: 10px 0 15px
  }
</style>
