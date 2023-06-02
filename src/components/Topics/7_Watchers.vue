<template>
    <div>
        <h2>Watchers</h2><hr/>
        <div class="volume-watcher">
            <h3>Volume Tracker (0-20)</h3>
            <p>Current Volume: {{volume}}</p>
            <button @click="volume -= 2">Decrease</button>
            <button @click="volume += 2">Increase</button>
        </div><hr/>
        <div class="immediate-deep">
            <h3>Immediate and Deep Properties</h3>
            <h4>Immediate - Calling API with movie name</h4>
            <input type="text" v-model="movie" />
            <span><b>Immediate API Call:</b> {{immediateApiCall}}</span>
            <h4>Deep - Calling API with nested changes in object</h4>
            <label>Enter Movie Title</label>
            <input type="text" v-model="movieInfo.title" />
            <label>Enter Movie Actor</label>
            <input type="text" v-model="movieInfo.actor" />
            <span><b>Deep API Call:</b> {{deepApiCall}}</span>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'Watchers',
    data() {
        return {
            volume: 0,
            movie: 'Batman',
            movieInfo: {
                title: '',
                actor: '',
            },
            immediateApiCall: '',
            deepApiCall: ''
        }
    },
    watch: {
        volume(newValue, oldValue) {
            if(newValue > oldValue && newValue === 16) {
                alert("Listening to high volume can damage your ears!")
            }
            if(newValue > 20 || newValue < 0) {
                alert("Volume level will always be in the range 0-20")
                this.volume = oldValue
            }
        },
        movie: {
            handler(newValue) {
                this.immediateApiCall = `Calling API with movie ${newValue}`
            },
            immediate: true,
        },
        movieInfo: {
            handler(newValue) {
                this.deepApiCall = `Calling API with movieInfo => Title: ${newValue.title} & Actor: ${newValue.actor}`
            },
            deep: true,
        }
    }
}
</script>

<style scoped>
.volume-watcher button {
    display: inline-block;
    font-size: 14px;
    padding: 8px 16px;
    margin-right: 10px;
}
.immediate-deep input {
    font-size: 14px;
    padding: 6px 12px;
    display: block;
    margin-bottom: 15px;
}
.immediate-deep label {
    font-size: 13px;
    font-weight: 600;
    display: block;
    margin-bottom: 10px;
}
.immediate-deep span {
    font-size: 12px;
    font-style: italic;
}
</style>