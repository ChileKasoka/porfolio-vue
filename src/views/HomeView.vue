<template>
    <div class=" min-h-screen block lg:flex justify-around">
        <div class="lg:ml-64 m-auto h-64 w-64">
            <img src="/me.png" alt="me" class="w-full h-full object-cover rounded-full" />
        </div>
        <div class=" text-center m-auto leading-normal p-5 space-y-5">
            <p class=" text-[#32363F] text-4xl lg:text-6xl xl:text-8xl">
                Hello world,
            </p>
            <h2 class=" text-4xl xl:text-6xl text-[#32363F]">
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
        <div class="lg:grid grid-rows-2 ">
            <div class="block lg:flex m-auto w-auto h-auto p-5">
                <div class="m-auto h-72 w-72 lg:mr-10">
                    <img src="/db.png" alt="me" class="w-full h-full object-cover rounded-lg" />
                </div>
                <div class="block m-auto w-full lg:w-4/5">
                    <div class="block lg:flex justify-center p-5 text-gray-500">
                        <div class=" block text-center w-full lg:w-2/6 lg:m-5 bg-slate-100 rounded-2xl">
                            <h2 class="p-2 text-xl">
                            <b>Experience</b> 
                            </h2>
                            <div class="p-2 text-xl text-center">
                                2 years+ <br> Frontend Experience/ Backend Technologies
                            </div>
                        </div>
                        <div class=" block text-center w-full lg:w-2/6 lg:m-5 mt-5 bg-slate-100 rounded-2xl">
                            <h2 class="text-xl p-2">
                                <b>Education</b>
                            </h2>
                            <p class="text-xl p-2">
                                BSc Bachelors Degree
                            </p>
                        </div>
                    </div>
                    <div class="w-2/3 text-center m-auto text-lg font-normal mb-3 text-gray-500">
                        Meet Chile, a seasoned full-stack developer with over 2 years of coding experience.
                        On the frontend, Chile is well-versed in HTML5, CSS3, and JavaScript,
                        utilizing popular frameworks such as React.js and Vuejs to create dynamic and
                        responsive user interfaces. With a keen eye for design.
                    </div>
                </div>
            </div>
            <div class="block lg:flex justify-between">
                <div class="m-auto order-1 lg:order-2 h-64 w-64">
                    <img src="/golang.png" alt="me" class="w-full h-full object-cover rounded-full" />
                </div>
                <div class="text-center order-2 lg:order-1 w-2/3 lg:w-2/4 flex-wrap p-4 m-auto text-lg font-normal h-fit text-gray-500">
                    <hr>
                    On the backend, I excel in server-side scripting languages like Golang, Java and Node.js,
                    building robust and scalable applications. Database management is second nature,
                    as Chile(Stunna) navigates through SQL and NoSQL databases like MySQL, MongoDB, and PostgreSQL.
                    RESTful API development is a forte,
                    allowing for smooth communication between the frontend and backend componentsss
                </div>
            </div>
        </div>
    </div>
    <div >
        <h1 class="text-center text-3xl">
            Experience
        </h1>
        <div class="grid grid-cols-1 md:flex m-auto">
            <div class="w-4/5 md:w-2/6 lg:w-2/6 p-2 m-auto space-y-5 mt-5 mb-5 bg-slate-100 rounded-2xl">
                <h1 class="text-center">
                    Frontend
                </h1>
                <div class="grid grid-cols-1 md:grid-cols-2 text-center ">
                    <div class="p-2">
                        HTML5
                    </div>
                    <div class="p-2">
                        CSS
                    </div>
                    <div class="p-2">
                        JavaScript
                    </div>
                    <div class="p-2">
                        Vuejs 
                    </div>
                    <div class="p-2">
                        React.js
                    </div>
                    <div class="p-2">
                        Tailwind
                    </div>
                </div>
            </div>
            <div class="w-4/5 md:w-2/6 lg:w-2/6 p-2 m-auto space-y-5 mt-5 mb-5 bg-slate-100 rounded-2xl">
                <h1 class="text-center">
                    Backend Technologies
                </h1>
                <div class="grid grid-cols-1 md:grid-cols-2 text-center ">
                    <div class="p-2">
                        Golang
                    </div>
                    <div class="p-2">
                        PHP
                    </div>
                    <div class="p-2">
                        JAVA
                    </div>
                    <div class="p-2">
                        Node js
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>