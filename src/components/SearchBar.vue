<template>
    <form @submit.prevent="scanHost()">
        <input
            type="text"
            placeholder="Enter hostname or ip"
            class="form-control p-2 m-2"
            v-model="host"
        />
        <button type="submit" class="btn btn-small btn-block btn-success">Search</button>
    </form>
    {{ response }}
</template>

<script>
import webSocket from 'ws';
export default {
    name: 'SearchBar',
    data() {
        return {
            host: "",
            response: ""
        }
    },
    methods: {
        scanHost() {
            // fetch(`http://localhost:8080/computer/?host=${this.host}`)
            //     .then(response => response.json())
            //     .then(data => {
            //         this.response = data;
            //         console.log(data)
            //     });
            const socket = new WebSocket('ws://localhost:4000');

            socket.addEventListener('open', function(event) {
                socket.send('Hello Server!');
            });
            // Listen for messages
            socket.addEventListener('message', function(event) {
                console.log('Message from server ', event.data);
            });
        }
    }
}
</script>