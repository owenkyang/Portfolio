<script>
    import {
		Timeline,
		TimelineItem,
		TimelineSeparator,
		TimelineDot,
		TimelineConnector,
		TimelineContent,
		TimelineOppositeContent
	} from 'svelte-vertical-timeline';

    import Step from "./Step.svelte";
    let steps = [
        {name: 'AI Expense Tracker', icon: "fa-solid fa-coins"},
        {name: 'Football Analyzer', icon: "fa-solid fa-futbol"},
        {name: 'Coming soon', icon: "fa-solid fa-code"}
    ];

    let experience = [
        {name: 'SWE Intern @ AT&T Labs', date: 'June 2024 - Aug 2024'},
        {name: 'Machine Learning Research Assistant @ AIRE Labs', date: 'June 2024 - Present'},
        {name: 'Research Assistant @ LASR Labs', date: 'June 2024 - Present'}
    ];
</script>

<main class="flex flex-col flex-1 p-4">
    <section id="introPage" class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14">
        <div class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10">
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                Hi! I'm <span class="poppins text-violet-400">Owen</span> Yang <br/> Data Science Student
                <span class="poppins text-violet-400"> <br/> @ UC San Diego</span> 
            </h2>
            <p class="text-base sm:text-lg md:text-xl">
            </p>
            <a class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins
            relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950 cursor-pointer" href="static/OwenYangResume.pdf" download>
                <div class="absolute top-0 right-full h-full bg-violet-400 opacity-20
                group-hover:translate-x-full z-0 duration-200"></div>
                <h4 class="relative z-9">Resume &rarr;</h4>
            </a>
        </div>
        <div class="relative shadow-2xl grid place-items-center">
            <img src={"images/profile.png"} alt="Profile Image" class="object-cover z-[2] max-h-[70vh]" width="535"/>
        </div>
    </section>
    <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
        <div class="flex flex-col gap-2 text-center">
            <h6 class="text-lg sm:text-xl md:text-2xl">
                A few of my endeavors.
            </h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                Curious to <span class="poppins text-violet-400">indulge</span> in my work?
            </h3>
        </div>
        <a href="https://github.com/owenkyang"
            target="_blank" class="mx-auto px-10 py-2 rounded-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0
            -mt-10 hover:border-violet-700 duration-200">
            <i class="fa-brands fa-github"></i>
            <p>GitHub</p>
        </a>
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
            <Step step={steps[0]}>
                <p>Keep track of your investments, expenses, and savings whilst getting financial advice from an AI assistant!</p>
                <!-- Add tech stack logos -->
            </Step>
            <Step step={steps[1]}></Step>
            <Step step={steps[2]}></Step>
        </div>
    </section>
    <section id="about" class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative">
        <div class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4">
            <h6 class="text-lg sm:text-xl md:text-2xl">Want to know more?</h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                A bit <span class="poppins text-violet-400">about</span> me.
            </h3>
        </div>
        <h3 class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">
            Experience
        </h3>
        <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
            <Timeline position="alternate">
            {#each experience as exp}
            <TimelineItem>
                <TimelineOppositeContent slot="opposite-content">
                    <p>{exp.date}</p>
                </TimelineOppositeContent>
                <TimelineSeparator>
                    <TimelineDot 
                    style = {'background-color: #A78BFA'}/>
                    <TimelineConnector />
                </TimelineSeparator>
                <TimelineContent style={'height: 200px;'}>
                    <h1 class = "text-md sm:text-lg md:text-xl">{exp.name}</h1>
                </TimelineContent>
            </TimelineItem>
            {/each}
        </Timeline>
        </div>
    </section>
</main>