<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">
                        I'm an example component.
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        mounted() {
            Echo.join(`chat`)
            .here((users) => {
                console.log("hre:",users);
            })
            .joining((user) => {
                console.log(`${user.name} joined`);
            })
            .leaving((user) => {
                console.log(`${user.name} leaved`);
            });
        }
    }
</script>
