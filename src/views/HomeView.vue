<template>
    <div class=" min-h-screen block lg:flex justify-around">
        <div class="lg:ml-64 m-auto h-64 w-64">
            <img src="/me.png" alt="me" class="w-full h-full object-cover rounded-full" />
        </div>
        <div class=" text-center m-auto leading-normal p-5 space-y-5">
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
        <h1 class="text-center text-[#054861]">
            Get to know me better
        </h1>
        <h3 class="text-4xl text-[#054861] text-center">
            About Me
        </h3>
        <div class="block lg:flex m-auto w-auto min-h-screen p-5">
            <div class="m-auto h-72 w-72 mr-10">
                <img src="/IMG_6200.png" alt="me" class="w-full h-full object-cover rounded-lg" />
            </div>
            <div class="block m-auto w-full lg:w-4/5">
                <div class="block md:flex justify-center p-5 text-gray-500">
                    <div class=" block text-center lg:w-2/6 m-5 md:mr-5 bg-slate-100 rounded-2xl">
                        <h2 class="p-2">
                        <b>Experience</b> 
                        </h2>
                        <div class="p-2 text-center">
                            2 years+ <br> Frontend Experience/ Backend Technologies
                        </div>
                    </div>
                    <div class=" block text-center lg:w-2/6 m-5 bg-slate-100 rounded-2xl">
                        <h2 class="p-2">
                            Education
                        </h2>
                        <p class="p-2">
                            BSc Bachelors Degree
                        </p>
                    </div>
                </div>

                <div class="w-2/3 text-center m-auto text-lg font-normal mb-3 text-gray-500">
                    Meet Chile, a seasoned full-stack developer with over 2 years of coding experience.
                    On the frontend, Chile is well-versed in HTML5, CSS3, and JavaScript,
                    utilizing popular frameworks such as React.js and Vuejs to create dynamic and
                    responsive user interfaces. With a keen eye for design 
                    <br><br>
                    On the backend, I excel in server-side scripting languages like Golang, Java and Node.js,
                    building robust and scalable applications. Database management is second nature,
                    as Chile(Stunna) navigates through SQL and NoSQL databases like MySQL, MongoDB, and PostgreSQL.
                    RESTful API development is a forte,
                    allowing for smooth communication between the frontend and backend components.
                </div>
            </div>
        </div>
    </div>
</template>