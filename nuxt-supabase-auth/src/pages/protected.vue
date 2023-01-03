<script setup lang="ts">
definePageMeta({
    middleware: 'authenticated'
});

const supaAuth = useSupabaseAuthClient().auth

const logout = async () => {
    const { error } = await supaAuth.signOut()
    if(error) {
        alert(error.message)
    } else {
        return navigateTo('/login');
    }
};
</script>

<template>
    <div>
        <h1>Protected Page</h1>
        <button @click="logout">Logout</button>
    </div>
</template>