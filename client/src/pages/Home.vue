<template>
    <Toast />
    <div class="px-5 py-3 m-0">
        <div class="surface-card p-4 shadow-2 border-round">
            <div class="font-medium text-3xl text-900 mb-3">
                Welcome,
                <span class="text-primary font-normal">
                    {{ store.state.root.user?.firstName }}
                    {{ store.state.root.user?.lastName }}
                </span>
            </div>
            <div class="text-500 mb-5">
                🔒 This is your protected user dashboard.
            </div>
            <ul class="list-none p-0 m-0 border-top-1 border-300">
                <li
                    class="flex align-items-center py-3 px-2 flex-wrap surface-50"
                >
                    <div class="text-500 w-full md:w-2 font-medium">Name</div>
                    <div class="text-900 w-full md:w-10">
                        {{ store.state.root.user?.firstName }}
                        {{ store.state.root.user?.lastName }}
                    </div>
                </li>
                <li class="flex align-items-center py-3 px-2 flex-wrap">
                    <div class="text-500 w-full md:w-2 font-medium">Email</div>
                    <div class="text-900 w-full md:w-10">
                        {{ store.state.root.user?.email }}
                    </div>
                </li>
                <li
                    class="flex align-items-center py-3 px-2 flex-wrap surface-50"
                >
                    <div class="text-500 w-full md:w-2 font-medium">
                        Phone Number
                    </div>
                    <div class="text-900 w-full md:w-10">
                        {{ store.state.root.user?.phoneNumber }}
                    </div>
                </li>
                <li class="flex align-items-center py-3 px-2 flex-wrap">
                    <div class="text-500 w-full md:w-2 font-medium">
                        Session Valid
                    </div>
                    <div class="text-900 md:w-10 flex flex-wrap">
                        <Tag
                            :value="
                                store.state.root.accessToken !== null
                                    ? true
                                    : false
                            "
                            severity="success"
                            class="uppercase"
                        ></Tag>
                    </div>
                </li>
                <li
                    class="flex align-items-center py-3 px-2 flex-wrap surface-50"
                >
                    <div class="text-500 w-full md:w-2 font-medium">
                        Account Count
                    </div>
                    <div class="text-900 w-full md:w-10">
                        <Tag
                            :value="store.state.root.user?.tokenVersion"
                            severity="info"
                        ></Tag>
                    </div>
                </li>
                <li class="flex align-items-center py-3 px-2 flex-wrap">
                    <div class="text-500 w-full md:w-2 font-medium">
                        Salary Expectation
                    </div>
                    <div class="text-900 w-full md:w-10">$15,000,000</div>
                </li>
                <li
                    class="flex align-items-center py-3 px-2 flex-wrap surface-50"
                >
                    <div class="text-500 w-full md:w-2 font-medium">Skills</div>
                    <div class="text-900 w-full md:w-10">
                        <Tag value="Algorithms" class="mr-2"></Tag>
                        <Tag
                            value="Javascript"
                            severity="success"
                            class="mr-2"
                        ></Tag>
                        <Tag
                            value="Python"
                            severity="warning"
                            class="mr-2"
                        ></Tag>
                        <Tag value="SQL" severity="danger"></Tag>
                    </div>
                </li>
                <li class="flex align-items-center py-3 px-2 flex-wrap">
                    <div class="text-500 w-full md:w-2 font-medium">
                        Accounts
                    </div>
                    <div class="text-900 w-full md:w-10">
                        <div class="grid mt-0 mr-0">
                            <div class="col-12 md:col-6">
                                <div
                                    class="p-3 border-1 border-300 border-round surface-50"
                                >
                                    <div class="text-900 mb-2">
                                        <i
                                            class="pi pi-youtube mr-2"
                                            style="color: #c4302b"
                                        ></i>
                                        <span class="font-medium">Youtube</span>
                                    </div>
                                    <div class="text-700">
                                        The Ultimate Platform To Share Videos
                                        And Tutorials.
                                    </div>
                                </div>
                            </div>
                            <div class="col-12 md:col-6">
                                <div
                                    class="p-3 border-1 border-300 border-round surface-50"
                                >
                                    <div class="text-900 mb-2">
                                        <i
                                            class="pi pi-github mr-2"
                                            style="color: #9d1bf2"
                                        ></i>
                                        <span class="font-medium">Github</span>
                                    </div>
                                    <div class="text-700">
                                        Share Your Work With The World.
                                    </div>
                                </div>
                            </div>
                            <div class="col-12 md:col-6">
                                <div
                                    class="p-3 border-1 border-300 border-round surface-50"
                                >
                                    <div class="text-900 mb-2">
                                        <i
                                            class="pi pi-reddit mr-2"
                                            style="color: #ff4300"
                                        ></i>
                                        <span class="font-medium">Reddit</span>
                                    </div>
                                    <div class="text-700">
                                        Speak Your Mind And Face The Wrath.
                                    </div>
                                </div>
                            </div>
                            <div class="col-12 md:col-6">
                                <div
                                    class="p-3 border-1 border-300 border-round surface-50"
                                >
                                    <div class="text-900 mb-2">
                                        <i
                                            class="pi pi-linkedin mr-2"
                                            style="color: #0274b3"
                                        ></i>
                                        <span class="font-medium">
                                            Linkined
                                        </span>
                                    </div>
                                    <div class="text-700">
                                        A Social Network... But For
                                        Professionals.
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from 'vue'
import { useStore } from '../store'
import { useToast } from 'primevue/usetoast'

export default defineComponent({
    name: 'Home',
    components: {},
    setup() {
        const store = useStore()
        const toast = useToast()

        onMounted(() => {
            if (store.state.root.user !== null) {
                toast.add({
                    severity: 'success',
                    summary: `Welcome ${
                        store.state.root.user.firstName +
                        ' ' +
                        store.state.root.user.lastName
                    }`,
                    detail: 'You are now logged in and authenticated.',
                    life: 5000,
                })
            }
        })

        return {
            store,
        }
    },
})
</script>

<style lang="scss" scoped></style>
