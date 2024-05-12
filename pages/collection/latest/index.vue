<script setup>
const books = [
    { name: 'ادب الأنبياء', author: 'محمد راضى', image: 'https://cdn.aseeralkotb.com/storage/media/305458/conversions/أدب-الأنبياء-26195-250x375-jpg.jpg', url: '/' },
    { name: 'المليونير الصغير', author: 'سام بيكبيسينجر', image: 'https://cdn.aseeralkotb.com/storage/media/358014/conversions/%D8%A7%D9%84%D9%85%D9%84%D9%8A%D9%88%D9%86%D9%8A%D8%B1-%D8%A7%D9%84%D8%B5%D8%BA%D9%8A%D8%B1-37536-250x375-webp.webp', url: '/' },
    { name: 'الويتشر ج1 - الأمنية الأخيرة', author: 'أندجي سابكوفسكي', image: 'https://cdn.aseeralkotb.com/storage/media/357561/conversions/%D8%A7%D9%84%D9%88%D9%8A%D8%AA%D8%B4%D8%B1-%D8%A7%D9%84%D8%A3%D9%85%D9%86%D9%8A%D8%A9-%D8%A7%D9%84%D8%A3%D8%AE%D9%8A%D8%B1%D8%A9-37435-250x375-webp.webp', url: '/' },
    { name: 'قصة الغراب الأسود', author: 'جميلة عبدالله', image: 'https://cdn.aseeralkotb.com/storage/media/357678/conversions/%D8%A7%D9%84%D9%81%D8%AA%D8%A7%D8%A9-%D8%A7%D9%84%D8%AA%D9%8A-%D8%AA%D8%B1%D9%83%D8%AA%D9%87%D8%A7-37353-250x375-webp.webp', url: '/' },
    { name: 'رحلة البحث عن السعادة', author: 'محمد علي', image: 'https://cdn.aseeralkotb.com/storage/media/357972/conversions/%D8%B3%D8%B1-%D8%A7%D9%84%D8%B1%D8%AD%D9%84%D8%A9-990-37523-250x375-webp.webp', url: '/' },
    { name: 'عالم الأحلام', author: 'سارة محمود', image: 'https://cdn.aseeralkotb.com/storage/media/357951/conversions/%D8%AF%D9%8A%D9%81-37518-250x375-webp.webp', url: '/' },
    { name: 'حكاية الوردة الضائعة', author: 'علي حسن', image: 'https://cdn.aseeralkotb.com/storage/media/357630/conversions/%D9%85%D8%B9%D8%B6%D9%84%D8%A9-%D8%A7%D9%84%D8%BA%D8%B2%D8%A7%D9%84-%D8%A7%D9%84%D8%A3%D9%85%D8%B1%D9%8A%D9%83%D9%8A-37453-250x375-webp.webp', url: '/' },
    { name: 'رحلة البحث عن الحقيقة', author: 'مريم علي', image: 'https://cdn.aseeralkotb.com/storage/media/357570/conversions/%D8%AA%D8%B9%D8%AA%D9%8A%D9%85-2-37438-250x375-webp.webp', url: '/' },
    { name: 'ألم الفراق', author: 'حسن محمود', image: 'https://cdn.aseeralkotb.com/storage/media/357765/conversions/%D8%B3%D8%A7%D8%B1%D9%82-%D8%A7%D9%84%D8%A8%D8%B1%D9%82-37479-250x375-webp.webp', url: '/' },
    { name: 'حكايات الشجاعة', author: 'نور محمد', image: 'https://cdn.aseeralkotb.com/storage/media/355353/conversions/%D8%A7%D9%84%D9%81%D9%83%D8%B1-%D8%A7%D9%84%D9%85%D9%81%D8%AA%D8%B1%D8%B3-37091-250x375-webp.webp', url: '/' },
    { name: 'دروس من الماضي', author: 'أحمد عبدالرحمن', image: 'https://cdn.aseeralkotb.com/storage/media/357375/conversions/%D8%A7%D9%84%D8%A3%D9%85%D9%8A%D8%B1-2-37380-250x375-webp.webp', url: '/' },
    { name: 'عالم المستقبل', author: 'ريم علي', image: 'https://cdn.aseeralkotb.com/storage/media/360221/conversions/%D8%A8%D8%B1%D8%A7%D8%A1%D8%A9-37970-250x375-webp.webp', url: '/' },
    { name: 'رحلة الاكتشاف', author: 'فاطمة علي', image: 'https://cdn.aseeralkotb.com/storage/media/305458/conversions/أدب-الأنبياء-26195-250x375-jpg.jpg', url: '/' },
    { name: 'أسرار الثراء', author: 'محمد حسين', image: 'https://cdn.aseeralkotb.com/storage/media/358014/conversions/%D8%A7%D9%84%D9%85%D9%84%D9%8A%D9%88%D9%86%D9%8A%D8%B1-%D8%A7%D9%84%D8%B5%D8%BA%D9%8A%D8%B1-37536-250x375-webp.webp', url: '/' },
    { name: 'رحلة النجاح', author: 'سارة أحمد', image: 'https://cdn.aseeralkotb.com/storage/media/357561/conversions/%D8%A7%D9%84%D9%88%D9%8A%D8%AA%D8%B4%D8%B1-%D8%A7%D9%84%D8%A3%D9%85%D9%86%D9%8A%D8%A9-%D8%A7%D9%84%D8%A3%D8%AE%D9%8A%D8%B1%D8%A9-37435-250x375-webp.webp', url: '/' },
    { name: 'سر السعادة', author: 'عبدالله علي', image: 'https://cdn.aseeralkotb.com/storage/media/357678/conversions/%D8%A7%D9%84%D9%81%D8%AA%D8%A7%D8%A9-%D8%A7%D9%84%D8%AA%D9%8A-%D8%AA%D8%B1%D9%83%D8%AA%D9%87%D8%A7-37353-250x375-webp.webp', url: '/' },
    { name: 'الطموح الكبير', author: 'نور محمد', image: 'https://cdn.aseeralkotb.com/storage/media/357972/conversions/%D8%B3%D8%B1-%D8%A7%D9%84%D8%B1%D8%AD%D9%84%D8%A9-990-37523-250x375-webp.webp', url: '/' },
    { name: 'حلم بلا حدود', author: 'حسين عبدالله', image: 'https://cdn.aseeralkotb.com/storage/media/357951/conversions/%D8%AF%D9%8A%D9%81-37518-250x375-webp.webp', url: '/' },
    { name: 'رحلة البحث عن السلام', author: 'ريم حسن', image: 'https://cdn.aseeralkotb.com/storage/media/357630/conversions/%D9%85%D8%B9%D8%B6%D9%84%D8%A9-%D8%A7%D9%84%D8%BA%D8%B2%D8%A7%D9%84-%D8%A7%D9%84%D8%A3%D9%85%D8%B1%D9%8A%D9%83%D9%8A-37453-250x375-webp.webp', url: '/' },
    { name: 'مفتاح الحياة', author: 'مريم علي', image: 'https://cdn.aseeralkotb.com/storage/media/357570/conversions/%D8%AA%D8%B9%D8%AA%D9%8A%D9%85-2-37438-250x375-webp.webp', url: '/' },
    { name: 'دروب النجاح', author: 'علي أحمد', image: 'https://cdn.aseeralkotb.com/storage/media/357765/conversions/%D8%B3%D8%A7%D8%B1%D9%82-%D8%A7%D9%84%D8%A8%D8%B1%D9%82-37479-250x375-webp.webp', url: '/' },
    { name: 'رحلة البحث عن القوة', author: 'ليلى حسن', image: 'https://cdn.aseeralkotb.com/storage/media/355353/conversions/%D8%A7%D9%84%D9%81%D9%83%D8%B1-%D8%A7%D9%84%D9%85%D9%81%D8%AA%D8%B1%D8%B3-37091-250x375-webp.webp', url: '/' },
    { name: 'سعادة الروح', author: 'أحمد محمود', image: 'https://cdn.aseeralkotb.com/storage/media/357375/conversions/%D8%A7%D9%84%D8%A3%D9%85%D9%8A%D8%B1-2-37380-250x375-webp.webp', url: '/' },
    { name: 'رحلة البحث عن النجوم', author: 'مريم علي', image: 'https://cdn.aseeralkotb.com/storage/media/360221/conversions/%D8%A8%D8%B1%D8%A7%D8%A1%D8%A9-37970-250x375-webp.webp', url: '/' },
];
</script>

<template>
    <TabsBar active="latest" />

    <section class="mt-10 bg-white">
        <hr class="mb-10">

        <BooksGrid :books="books" class="mt-6" />

        <div class="w-full flex justify-center mt-6">
            <button type="button" class="text-white bg-gradient-to-r from-red-400 via-red-500 to-red-600 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-red-300 dark:focus:ring-red-800 shadow-lg shadow-red-500/50 dark:shadow-lg dark:shadow-red-800/80 font-medium rounded-lg text-sm px-5 py-2.5 text-center me-2 mb-2">الـــمـــزيد...</button>
        </div>
        </section>
    <section class="mb-16" />
</template>