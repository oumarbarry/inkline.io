<script lang="ts">
import { defineComponent, onMounted } from 'vue';
import { definePageMeta, useContent, useContentHead } from '#imports';
import { docsEventBus } from '~/utils';

export default defineComponent({
    setup() {
        definePageMeta({
            layout: 'docs'
        });

        onMounted(() => {
            docsEventBus.emit('page:mounted', new Event('page:mounted'));
        });

        return {};
    }
});
</script>

<template>
    <article id="page">
        <ContentDoc>
            <template #not-found>
                <AppError />
            </template>
        </ContentDoc>
    </article>
</template>
