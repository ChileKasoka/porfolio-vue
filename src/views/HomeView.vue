<template>
    <div class=" min-h-screen flex justify-around">
        <div class="ml-64 m-auto h-64 w-64">
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
                Aspiring Full stack.
            </h1>
            <button onsubmit="handleDownload()" class=" hover:bg-[#ebe8e8] text-[#054861] w-44 h-12 rounded-full bg-[#BFBBBB]">
                Download CV
            </button>
        </div>
    </div>
</template>