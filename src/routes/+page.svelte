<script>
    import { 
        Layout
    } from 'lucide-svelte';
</script>

<div class="min-h-screen bg-gray-50 p-8">
    <h1 class="text-3xl font-bold text-center text-gray-800 mb-12">App Dashboard</h1>
    
    <div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">

        <a href="/layouts" class="group">
            <div class="bg-white p-6 rounded-xl shadow-sm hover:shadow-md transition-all border border-gray-100 group-hover:border-blue-100">
                <div class="mb-4 text-blue-500 group-hover:text-blue-600">
                    <Layout size={32} />
                </div>
                <h2 class="text-xl font-semibold text-gray-700 group-hover:text-blue-600">Layouts</h2>
                <p class="text-gray-500 mt-2">Page layouts and structure components</p>
            </div>
        </a>
    </div>
</div>
