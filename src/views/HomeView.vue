<template>
    <div class=" min-h-screen block lg:flex justify-around">
        <div class="lg:ml-64 m-auto h-64 w-64">
            <img src="/me.png" alt="me" class="w-full h-full object-cover rounded-full" />
        </div>
        <div class=" text-center m-auto leading-normal space-y-5">
            <p class=" text-[#32363F] text-8xl">
                Hello world,
            </p>
            <h2 class=" text-6xl text-[#32363F]">
                I'm Chile,
            </h2>
            <h1 class=" text-4xl text-[#054861]">
                Full Stack Dev.
            </h1>
            <button onsubmit="handleDownload()" class=" hover:bg-[#ebe8e8] text-[#054861] w-44 h-12 rounded-full bg-[#BFBBBB]">
                Download CV
            </button>
        </div>
    </div>
    <div class=" leading-normal ">
        <h1 class="text-center">
            Get to know me better
        </h1>
        <h3 class="text-center text-5xl">
            About Me
        </h3>
        <div class="flex m-auto w-4/5 min-h-screen">
            <div class="m-auto h-72 w-72 mr-10">
                <img src="/IMG_6200.png" alt="me" class="w-full h-full object-cover rounded-lg" />
            </div>
            <div class="block m-auto w-4/5">
                <div class="block md:flex justify-center">
                    <div class=" block text-center w-2/6 mr-5 bg-slate-100 rounded-2xl">
                        <h2 class="p-2">
                        <b>Experience</b> 
                        </h2>
                        <div class="p-2 text-center">
                            2 years+ <br> Frontend Experience/ Backend Technologies
                        </div>
                    </div>
                    <div class=" block text-center w-2/6 bg-slate-100 rounded-2xl">
                        <h2 class="p-2">
                            Education
                        </h2>
                        <p class="p-2">
                            BSc Bachelors Degree
                        </p>
                    </div>
                </div>

                <div class="w-2/3 text-center m-auto p-5">
                    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nobis illo at enim doloribus, 
                    odit aspernatur praesentium deserunt eius dignissimos exercitationem 
                    ipsam tenetur nemo cupiditate repellendus laudantium itaque quidem aliquam adipisci.
                </div>
            </div>
        </div>
    </div>
</template>