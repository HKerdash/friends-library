<script setup>
const categories = [
    { name: 'علوم الحاسب', url: '/' },
    { name: 'الذكاء الاصطناعي', url: '/' },
    { name: 'تطوير الويب', url: '/' },
    { name: 'قواعد البيانات', url: '/' },
    { name: 'البرمجة بلغة Python', url: '/' },
    { name: 'الشبكات وأمن المعلومات', url: '/' },
    { name: 'تطبيقات الهاتف المحمول', url: '/' },
    { name: 'تصميم واجهات المستخدم', url: '/' },
    { name: 'تطوير الألعاب', url: '/' },
    { name: 'تحليل البيانات', url: '/' },
    { name: 'الحوسبة السحابية', url: '/' },
];

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
    <section class="bg-slate-500 bg-[url('https://c1.wallpaperflare.com/path/127/366/443/library-book-bookshelf-read-fb757647c9e6825890e1ad3d86d286fe.jpg')]">
        <div class="py-4 px-2 mx-auto text-center lg:py-16 z-10 relative">

            <div class="absolute inset-0 bg-no-repeat hero"></div>
            <div class="relative px-2 py-12 mx-auto max-w-screen-2xl lg:py-28">
                <header class="mb-4">
                    <h1 class="text-6xl font-extrabold tracking-tighter text-center text-white"
                        style="text-shadow: 2px 5px 0 rgb(0 0 0 / 30%)">مكتبة الأصدقاء </h1>
                </header>
                <div class="flex justify-center mt-20 mb-4 search">
                    <div class="flex mb-0 w-full shadow-xl sm:w-3/5 focus:scale-110 relative">
                        <div class="w-full">
                            <div class="w-full">
                                <div class="w-full flex">
                                    <input type="search" placeholder="ابحث عن كتاب..."
                                        class="inline-block flex-1 px-4 h-16 text-sm leading-8 rtl:rounded-r-lg ltr:rounded-l-lg border transition-all duration-200 ease-in outline-none border-blue-200 focus:border-red-600 focus:ring-0"
                                        aria-label="ابحث عن كتاب...">
                                    <button
                                        class="flex items-center px-6 h-16 text-2xl text-white bg-red-600 rounded-r-none rtl:rounded-l-lg ltr:rounded-r-lg transition-all duration-200 ease-in hover:bg-red-600-darker"
                                        aria-label="search-button">
                                        <Icon name="heroicons-solid:search" />
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="flex justify-center space-x-4 space-x-reverse mt-20 mb-4">
                    <div class="space-y-6 w-full lg:w-1/2">
                        <div class="grid gap-2 justify-items-stretch grid-cols-2">
                            <NuxtLink to="/" class="flex relative justify-between items-center hover:no-underline">
                                <div
                                    class="absolute inset-0 bg-red-500 rounded-lg mix-blend-multiply transition-all duration-200 ease-in-out hover:bg-red-400">
                                </div>
                                <div class="flex-1 p-4 font-extrabold text-center text-gray-500">كتب ورقية</div>
                            </NuxtLink>
                            <NuxtLink to="/" class="flex relative justify-between items-center hover:no-underline">
                                <div
                                    class="absolute inset-0 bg-red-500 rounded-lg mix-blend-multiply transition-all duration-200 ease-in-out hover:bg-red-400">
                                </div>
                                <div class="flex-1 p-4 font-extrabold text-center text-gray-500">كتب اونلاين </div>
                            </NuxtLink>
                        </div>
                    </div>
                </div>

                <div class="flex justify-center space-x-4 space-x-reverse mt-20 overflow-x-auto whitespace-nowrap">
                    <div class="space-y-6 w-full">
                        <div class="grid gap-2 grid-cols-2 md:grid-cols-6">
                            <div v-for="(item, index) in categories" :key="index">
                                <NuxtLink :href="item.url"
                                    class="flex relative justify-between items-center hover:no-underline whitespace-nowrap">
                                    <div
                                        class="absolute inset-0 bg-gray-600 rounded-lg mix-blend-overlay transition-all duration-200 ease-in-out hover:bg-gray-700">
                                    </div>
                                    <div class="flex-1 p-4 text-xs font-extrabold text-center text-white">{{ item.name }}</div>
                                </NuxtLink>
                            </div>
                            <NuxtLink to="/" class="flex relative justify-between items-center hover:no-underline">
                                <div
                                    class="absolute inset-0 bg-red-500 rounded-lg mix-blend-multiply transition-all duration-200 ease-in-out hover:bg-red-400">
                                </div>
                                <div class="flex-1 p-4 text-xs font-extrabold text-center text-gray-500">المزيد</div>
                            </NuxtLink>
                        </div>
                    </div>
                </div>

            </div>
        </div>
        <div class="bg-gradient-to-b to-transparent from-gray-800 w-full h-full absolute top-0 left-0 z-0"></div>
    </section>

    <TabsBar/>

    <section class="mt-10">
        <hr class="mb-10">

        <BooksGrid :books="books" name="أحدث الكتب" class="mt-6" />
        <BooksGrid :books="books" name="كتب إسلامية" class="mt-6" />

        <div class="w-full flex justify-center mt-6">
            <button type="button" class="text-white bg-gradient-to-r from-red-400 via-red-500 to-red-600 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-red-300 dark:focus:ring-red-800 shadow-lg shadow-red-500/50 dark:shadow-lg dark:shadow-red-800/80 font-medium rounded-lg text-sm px-5 py-2.5 text-center me-2 mb-2">الـــمـــزيد...</button>
        </div>
        </section>
    <section class="mb-16" />
</template>