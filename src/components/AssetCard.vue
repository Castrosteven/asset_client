<template>
    <div class="card">
        <div class="container">
            <div class="row">
                <div class="col">
                    <h6>{{ computer.name }}</h6>
                </div>
            </div>
            <div class="row">
                <div class="col-auto">
                    {{ computer.type }}
                    <i :class="assetType(computer.type)"></i>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts">
export default {
    name: "ComputerCard",
    created() { console.log('created') },
    data() {
        return {
        };
    },
    props: {
        computer: {
            default: { id: 0, name: 'computer', type: '', },
        }
    },
    methods: {
        assetType(type: string): string {
            let response = ''
            type == 'Desktop' ? response = 'fas fa-desktop' : type == 'Printer' ? response = 'fas fa-print' : type == 'VoipPhone' ? response = 'fas fa-phone' : type == 'Smartphone' ? response = 'fas fa-mobile-alt' : type == 'Server' ? response = 'fas fa-server' : null
            return response
        }
    },
};
</script>

<style>
.card:hover {
    box-shadow: 0 15px 10px -10px rgba(31, 31, 31, 0.5);
    transition: all 0.3s ease;
}
</style>