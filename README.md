<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ultimate Car Camping Checklist</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght=300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }
        .cb-input:checked + span { text-decoration: line-through; color: #94a3b8; }
        .cb-input:checked + span a { text-decoration: line-through; color: #94a3b8 !important; }
        /* Hide scrollbars for a cleaner navigation look */
        .scrollbar-none::-webkit-scrollbar { display: none; }
        .scrollbar-none { -ms-overflow-style: none; scrollbar-width: none; }
    </style>
</head>
<body class="bg-slate-50 min-h-screen pb-20 relative">

    <!-- Header Section -->
    <header class="bg-emerald-800 text-white py-12 px-4 shadow-md text-center relative overflow-hidden">
        <div class="absolute inset-0 opacity-10 bg-[radial-gradient(#fff_1px,transparent_1px)] [background-size:16px_16px]"></div>
        <div class="max-w-3xl mx-auto relative z-10">
            <span class="text-emerald-300 font-bold tracking-widest text-xs uppercase bg-emerald-900/50 px-3 py-1 rounded-full">Hit The Road</span>
            <h1 class="text-3xl md:text-5xl font-extrabold mt-3 tracking-tight">Car Camping Checklist</h1>
            <p class="text-emerald-100/80 mt-2 font-light max-w-xl mx-auto text-sm md:text-base">
                Filter by category, check off your gear as you pack, and ensure you never leave the essentials behind!
            </p>
            <!-- Highlighted Recommendation Sentence -->
            <div class="mt-4 inline-block">
                <p class="text-emerald-200 font-medium text-xs md:text-sm bg-emerald-900/40 py-2 px-4 rounded-xl border border-emerald-700/50 max-w-lg mx-auto">
                    💡 Green text indicates a clickable link to gear we personally use and highly recommend!
                </p>
            </div>
        </div>
    </header>

    <!-- Sticky Navigation & Progress Bar -->
    <div class="sticky top-0 z-40 bg-white/95 backdrop-blur border-b border-slate-200 shadow-sm py-4 mb-8">
        <div class="max-w-4xl mx-auto px-4">
            <!-- Progress Section -->
            <div class="mb-4">
                <div class="flex justify-between text-xs font-semibold text-slate-600 mb-1">
                    <span>PACKING PROGRESS</span>
                    <span id="progress-text">0% (0/0)</span>
                </div>
                <div class="w-full bg-slate-100 rounded-full h-2.5 overflow-hidden">
                    <div id="progress-bar" class="bg-emerald-500 h-2.5 rounded-full transition-all duration-300 w-0"></div>
                </div>
            </div>

            <!-- Jump-To Mention Helper Label -->
            <div class="flex items-center justify-between mb-2">
                <span class="text-[10px] md:text-xs font-bold tracking-wider text-slate-500 uppercase">
                    Quick Filter (click a category to view only those items):
                </span>
            </div>

            <!-- Categories Horizontal Filter Scroll with Enhanced Contrast Buttons -->
            <div class="flex items-center gap-2 overflow-x-auto pb-2 scrollbar-none border-t border-slate-100 pt-3">
                <button onclick="filterCategory('all')" class="filter-btn px-4 py-1.5 rounded-full text-xs font-bold whitespace-nowrap transition-all duration-150 bg-emerald-700 text-white shadow-md border border-emerald-800 scale-[1.02]" data-cat="all">All Items</button>
                <button onclick="filterCategory('sleeping')" class="filter-btn px-4 py-1.5 rounded-full text-xs font-semibold whitespace-nowrap transition-all duration-150 bg-white text-slate-700 hover:bg-slate-100 border border-slate-300 hover:border-slate-400 hover:shadow-sm hover:scale-[1.02] active:scale-[0.98]" data-cat="sleeping">🏔️ Sleeping & Tent</button>
                <button onclick="filterCategory('clothing')" class="filter-btn px-4 py-1.5 rounded-full text-xs font-semibold whitespace-nowrap transition-all duration-150 bg-white text-slate-700 hover:bg-slate-100 border border-slate-300 hover:border-slate-400 hover:shadow-sm hover:scale-[1.02] active:scale-[0.98]" data-cat="clothing">👕 Clothing</button>
                <button onclick="filterCategory('hygiene')" class="filter-btn px-4 py-1.5 rounded-full text-xs font-semibold whitespace-nowrap transition-all duration-150 bg-white text-slate-700 hover:bg-slate-100 border border-slate-300 hover:border-slate-400 hover:shadow-sm hover:scale-[1.02] active:scale-[0.98]" data-cat="hygiene">🧼 Hygiene</button>
                <button onclick="filterCategory('cooking')" class="filter-btn px-4 py-1.5 rounded-full text-xs font-semibold whitespace-nowrap transition-all duration-150 bg-white text-slate-700 hover:bg-slate-100 border border-slate-300 hover:border-slate-400 hover:shadow-sm hover:scale-[1.02] active:scale-[0.98]" data-cat="cooking">🍳 Cooking Gear</button>
                <button onclick="filterCategory('dog')" class="filter-btn px-4 py-1.5 rounded-full text-xs font-semibold whitespace-nowrap transition-all duration-150 bg-white text-slate-700 hover:bg-slate-100 border border-slate-300 hover:border-slate-400 hover:shadow-sm hover:scale-[1.02] active:scale-[0.98]" data-cat="dog">🐾 Dog Essentials</button>
            </div>
        </div>
    </div>

    <!-- Main Checklist Content -->
    <main class="max-w-4xl mx-auto px-4 space-y-8">

        <!-- Sleeping & Tent -->
        <div class="category-block bg-white rounded-2xl shadow-sm border border-slate-200/80 overflow-hidden" data-category="sleeping">
            <div class="bg-slate-900 px-6 py-4 border-b border-slate-100">
                <h3 class="font-bold text-white text-base tracking-wide">Sleeping & Tent</h3>
            </div>
            <div class="p-6 grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-3.5">
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Tent + footprint/tarp</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Sleeping bags</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Sleeping pads or air mattress</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Pillows</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors"><a href="https://amzn.to/4nMkKe8" target="_blank" class="text-emerald-600 underline font-semibold hover:text-emerald-800">Sleeping mask</a></span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Extra blankets</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors"><a href="https://amzn.to/4nJ3hDj" target="_blank" class="text-emerald-600 underline font-semibold hover:text-emerald-800">Camp chairs</a></span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Tarp or canopy for shade/rain</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Headlamps</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors"><a href="https://amzn.to/4a2fqgU" target="_blank" class="text-emerald-600 underline font-semibold hover:text-emerald-800">Inflatable lamp</a></span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Extra batteries</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Gloves (mornings can be cold)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Hammock</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Bear spray</span>
                </label>
            </div>
        </div>

        <!-- Clothing -->
        <div class="category-block bg-white rounded-2xl shadow-sm border border-slate-200/80 overflow-hidden" data-category="clothing">
            <div class="bg-slate-900 px-6 py-4 border-b border-slate-100">
                <h3 class="font-bold text-white text-base tracking-wide">Clothing</h3>
            </div>
            <div class="p-6 grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-3.5">
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Warm evening pants</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Warm sweater/fleece</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Packable puffy jacket</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Rain jacket (always!)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Hiking pants/shorts</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Socks + Extra warm socks for the evening</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Underwear</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Sleep clothes (PJ)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">T-shirt or any comfy top for moving and relaxing</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Swimsuit</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Hat/cap</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Sunglasses</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Hiking boots/shoes</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Warm underlayer</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Sandals/camp shoes</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Sports bra</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Gloves/toque (AT ALL TIMES) i always have a toque to sleep even in the middle of july, trust me.</span>
                </label>
            </div>
        </div>

        <!-- Hygiene & Toiletries -->
        <div class="category-block bg-white rounded-2xl shadow-sm border border-slate-200/80 overflow-hidden" data-category="hygiene">
            <div class="bg-slate-900 px-6 py-4 border-b border-slate-100">
                <h3 class="font-bold text-white text-base tracking-wide">Hygiene & Toiletries</h3>
            </div>
            <div class="p-6 grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-3.5">
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Toothbrush + toothpaste</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Face wash + moisturizer</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Shampoo + conditioner (if necessary)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Body wash/soap</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Deodorant</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Sunscreen</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Bug spray</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Toilet paper (always)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Wet wipes</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Hand sanitizer</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Microfiber towel (if swimming)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Lip balm</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Feminine hygiene products</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Prescription medication</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">First aid kit</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Nail clippers</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Shower sandals</span>
                </label>
            </div>
        </div>

        <!-- Cooking Gear -->
        <div class="category-block bg-white rounded-2xl shadow-sm border border-slate-200/80 overflow-hidden" data-category="cooking">
            <div class="bg-slate-900 px-6 py-4 border-b border-slate-100">
                <h3 class="font-bold text-white text-base tracking-wide">Cooking Gear</h3>
            </div>
            <div class="p-6 grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-3.5">
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Camping stove</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Fuel/canisters</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Lighter or waterproof matches</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Pots + pans</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Cooking utensils</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Sharp knife (we like Opinel)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Cutting board</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Plates/bowls</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Mugs/cups</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors"><a href="https://amzn.to/4dEmDES" target="_blank" class="text-emerald-600 underline font-semibold hover:text-emerald-800">Water filter (if necessary)</a></span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Reusable water bottles + water</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Camel pack</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Cooler</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Ice packs/ice</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors"><a href="https://amzn.to/4dq7gRN" target="_blank" class="text-emerald-600 underline font-semibold hover:text-emerald-800">Dish soap (use a biodegradable one)</a></span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Sponge/dish towel</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Paper towels</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Garbage bag (pack in/pack out everything)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors"><a href="https://amzn.to/4uXUwYq" target="_blank" class="text-emerald-600 underline font-semibold hover:text-emerald-800">Coffee maker</a></span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors"><a href="https://amzn.to/4uqrsJ7" target="_blank" class="text-emerald-600 underline font-semibold hover:text-emerald-800">Bug repellent</a></span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Coffee / tea</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Olive oil</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Salt/pepper</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Can opener</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Wine opener</span>
                </label>
            </div>
        </div>

        <!-- Dog Essentials -->
        <div class="category-block bg-white rounded-2xl shadow-sm border border-slate-200/80 overflow-hidden" data-category="dog">
            <div class="bg-slate-900 px-6 py-4 border-b border-slate-100">
                <h3 class="font-bold text-white text-base tracking-wide">Dog Essentials</h3>
            </div>
            <div class="p-6 grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-3.5">
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Dog food</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Water bowls</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Extra water</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Leash</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Harness</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Bell</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Long line/tie-out</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors"><a href="https://amzn.to/4uqs3dP" target="_blank" class="text-emerald-600 underline font-semibold hover:text-emerald-800">Collar for night time</a></span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Dog bed or blanket (make sure you use something isolated since the nights can get cold)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Towels for muddy paws</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Poop bags</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Treats - we use cheese for high reward and better recall ;)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Toys / chews</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors"><a href="https://amzn.to/4f923PH" target="_blank" class="text-emerald-600 underline font-semibold hover:text-emerald-800">Tick remover/bug repellent</a></span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors">Dog swimming jacket (if applicable)</span>
                </label>
                <label class="flex items-start gap-3.5 px-3 py-2.5 rounded-xl hover:bg-slate-50 transition-colors cursor-pointer group select-none border border-transparent hover:border-slate-100">
                    <input type="checkbox" onchange="updateProgress()" class="cb-input mt-0.5 h-4.5 w-4.5 rounded text-emerald-600 focus:ring-emerald-500 border-slate-300 accent-emerald-600 transition-all">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900 transition-colors"><a href="https://amzn.to/4nL8kD9" target="_blank" class="text-emerald-600 underline font-semibold hover:text-emerald-800">Portable Crate</a> - we like this so he can have a place to settle at camp</span>
                </label>
            </div>
        </div>

    </main>

    <!-- Interactive Scripts -->
    <script>
        // Track checked elements dynamically
        function updateProgress() {
            const checkboxes = document.querySelectorAll('.cb-input');
            const total = checkboxes.length;
            const checked = document.querySelectorAll('.cb-input:checked').length;
            
            const pct = total > 0 ? Math.round((checked / total) * 100) : 0;
            
            // Update percentage bar and text
            document.getElementById('progress-text').textContent = `${pct}% (${checked}/${total})`;
            document.getElementById('progress-bar').style.width = `${pct}%`;
        }

        // Handle active categories filtering
        function filterCategory(category) {
            // Update button styles to reflect active category with enhanced high-contrast states
            const filterButtons = document.querySelectorAll('.filter-btn');
            filterButtons.forEach(btn => {
                if (btn.getAttribute('data-cat') === category) {
                    btn.className = "filter-btn px-4 py-1.5 rounded-full text-xs font-bold whitespace-nowrap transition-all duration-150 bg-emerald-700 text-white shadow-md border border-emerald-800 scale-[1.02]";
                } else {
                    btn.className = "filter-btn px-4 py-1.5 rounded-full text-xs font-semibold whitespace-nowrap transition-all duration-150 bg-white text-slate-700 hover:bg-slate-100 border border-slate-300 hover:border-slate-400 hover:shadow-sm hover:scale-[1.02] active:scale-[0.98]";
                }
            });

            // Toggle category blocks visibility
            const blocks = document.querySelectorAll('.category-block');
            blocks.forEach(block => {
                if (category === 'all' || block.getAttribute('data-category') === category) {
                    block.classList.remove('hidden');
                } else {
                    block.classList.add('hidden');
                }
            });
        }

        // Initialize progress tracker when DOM renders
        window.addEventListener('DOMContentLoaded', () => {
            updateProgress();
        });
    </script>
</body>
</html>
