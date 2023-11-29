<script>
    let input;
    let errMsg;

    const handleSubmit = () => {
        console.log(input.value);
        if(input.value === '') {
            errMsg.innerHTML = 'Please add a link';
            input.classList.add('border-red');
        } else if(!validURL(input.value)) {
            errMsg.innerHTML = 'Please add a valid link';
            input.classList.add('border-red');
        } else {
            errMsg.innerHTML = '';
            input.classList.remove('border-red');
            alert('Link added!');
        }
    };

    const validURL = (str) => {
        let pattern = new RegExp(
            '^(https?:\\/\\/)?' + // protocol
            '((([a-z\\d]([a-z\\d-]*[a-z\\d])*)\\.)+[a-z]{2,}|' +
            '((\\d{1,3}\\.){3}\\d{1,3}))' +
            '(\\:\\d+)?(\\/[-a-z\\d%_.~+]*)*' +
            '(\\?[;&a-z\\d%_.~+=-]*)?' +
            '(\\#[-a-z\\d_]*)?$',
            'i'
        )
        return !!pattern.test(str)
    }
</script>
<!-- Nav Container -->
<nav class="relative container mx-auto p-6">
    <!-- Flex Container for all Items -->
    <div class="flex items-center justify-between">
        <!-- Flex Container for Logo/Menu -->
        <div class="flex items-center space-x-20">
            <!-- Logo -->
            <img src="images/logo.svg" alt="">
            <!-- Left Menu -->
            <div class="hidden space-x-8 font-bold lg:flex">
                <a href="#" class="text-grayishViolet hover:text-veryDarkViolet">Features</a>
                <a href="#" class="text-grayishViolet hover:text-veryDarkViolet">Pricing</a>
                <a href="#" class="text-grayishViolet hover:text-veryDarkViolet">Resources</a>
            </div>
            
        </div>
        <!-- Right Buttons Menu -->
        <div class="hidden items-center space-x-6 font-bold text-grayishViolet lg:flex">
            <div class="hover:text-veryDarkViolet">Login</div>
            <a href="#" class="px-8 py-3 font-bold text-white bg-cyan rounded-full hover:opacity-70">Sign Up</a>
        </div>
        <!-- TODO: Hamburger Menu -->
    </div>
    <!-- TODO: Mobile Menu -->
</nav>
<!-- Hero section -->
<section id="hero">
    <!-- Hero Container -->
    <div class="container flex flex-col-reverse mx-auto p-6 lg:flex-row">
        <!-- Contentet Container -->
        <div class="flex flex-col space-y-10 mb-44 lg:mt-16 lg:w-1/2 xl:mb-52">
            <h1 class="text-5xl font-bold text-center lg:text-6xl lg:max-w-md lg:text-left">
                More than shorter links
            </h1>
            <p class="text-2xl text-center text-gray-400 lg:max-w-md lg:text-left">
                Lorem, ipsum dolor sit amet consectetur adipisicing elit. Blanditiis omnis praesentium amet facere unde, earum ipsam a quisquam. Vitae soluta, asperiores labore nam facilis ut commodi rem.
            </p>
            <div class="mx-auto lg:mx-0">
                <a href="#" class="py-5 px-10 text-2xl font-bold text-white bg-cyan rounded-full lg:py-4 hover:opacity-70">Get Started</a>
            </div>
        </div>

        <!-- Image -->
        <div class="mb-24 mx-auto md:w-180 lg:mb-0 lg:w-1/2">
            <img src="images/illustration-working.svg" alt="">
        </div>
    </div>
</section>

<!-- Shorten Section -->
<section id="shorten" class="relative bg-gray-100">
    <!-- Shorten Container -->
    <div class="max-w-4xl mx-auto p-6 space-y-6">
        <!-- Form -->
        <form 
            on:submit|preventDefault={handleSubmit}
            id="link-form" 
            class="relative flex flex-col w-full p-10 -mt-20 space-y-4 bg-darkViolet rounded-lg md:flex-row md:space-y-0 md:space-x-3">
            <input 
                bind:this={input}
                type="text" 
                class="flex-1 p-3 border-2 rounded-lg placeholder-yellow-500 focus:outline-none" 
                placeholder="Shorten a link here!" 
                id="link-input"
            >
            <button class="px-10 py-3 text-white bg-cyan rounded-lg hover:bg-cyanLight focus:outline-none md:py-2">Shorten It!</button>
            <!-- Error messages -->
            <div bind:this={errMsg} id="err-msg" class="absolute left-7 bottom-3 text-red text-sm italic">

            </div>
        </form>
        <!-- Link 1 -->
        <div class="flex flex-col items-center justify-between w-full p-6 bg-white rounded-lg md:flex-row">
            <p class="font-bold text-center text-veryDarkViolet md:text-left">
                https://joel-uzcategui.com
            </p>
            <div class="flex flex-col items-center justify-end flex-1 space-x-4 space-y-2 md:flex-row md:space-y-0">
                <div class="font-bold text-cyan">https://rel.ink.k4IKyk</div>
                <button class="p-2 px-8 text-white bg-cyan rounded-lg hover:opacity-70 focus:outline-none">
                    Copy
                </button>
            </div>
        </div>
        <!-- Link 2 -->
        <div class="flex flex-col items-center justify-between w-full p-6 bg-white rounded-lg md:flex-row">
            <p class="font-bold text-center text-veryDarkViolet md:text-left">
                https://joel-uzcategui.com
            </p>
            <div class="flex flex-col items-center justify-end flex-1 space-x-4 space-y-2 md:flex-row md:space-y-0">
                <div class="font-bold text-cyan">https://rel.ink.k4IKyk</div>
                <button class="p-2 px-8 text-white bg-darkViolet rounded-lg hover:opacity-70 focus:outline-none">
                    Copy
                </button>
            </div>
        </div>
        <!-- Link 3 -->
        <div class="flex flex-col items-center justify-between w-full p-6 bg-white rounded-lg md:flex-row">
            <p class="font-bold text-center text-veryDarkViolet md:text-left">
                https://joel-uzcategui.com
            </p>
            <div class="flex flex-col items-center justify-end flex-1 space-x-4 space-y-2 md:flex-row md:space-y-0">
                <div class="font-bold text-cyan">https://rel.ink.k4IKyk</div>
                <button class="p-2 px-8 text-white bg-cyan rounded-lg hover:opacity-70 focus:outline-none">
                    Copy
                </button>
            </div>
        </div>
    </div>
</section>

<!-- Stats Section -->
<section id="stats" class="py-24 bg-gray-100">
    <div class="container mx-auto px-3">
        <h2 class="text-4xl mb-6 font-bold text-center">
            Advanced Statistics
        </h2>
        <p class="max-w-xs mx-auto text-center text-gray-400 md:max-w-md">
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis sapiente eaque ea ullam vero dignissimos.
        </p>
    </div>
</section>

<!-- Features Box Section -->
<section id="features" class="pb-32 bg-gray-100">
    <div class="relative container flex flex-col items-start px-6 mx-auto md:flex-row md:space-x-7">
        <!-- Horizontal Line -->
        <div class="hidden absolute top-24 w-10/12 left-16 h-3 bg-cyan md:block"></div>
        <!-- Vertical Line -->
        <div class="absolute w-2 left-1/2 h-full -ml-1 bg-cyan md:hidden"></div>
        <!-- Box 1 -->
        <div class="relative flex flex-col p-6 space-y-6 bg-white rounded-lg md:w-1/3">
            <!-- Image Positioning -->
            <div class="absolute -ml-10 left-1/2 -top-10 md:left-16">
                <!-- Image Container for Background & Center -->
                <div class="flex items-center justify-center w-20 h-20 p-4 rounded-full bg-veryDarkViolet">
                    <!-- Image -->
                    <img src="images/icon-brand-recognition.svg" alt="">
                </div>
            </div>
            <h5 class="pt-6 text-xl font-bold text-center capitalize md:text-left">Brand Recognition</h5>
            <p class="text-center text-gray-400md:text-left">
                Lorem ipsum dolor sit amet consectetur, adipisicing elit. In quibusdam ad dolore quae dolorum facilis eligendi delectus voluptates ipsam explicabo, pariatur eos distinctio! Doloribus maiores eos non esse aliquam fuga.
            </p>
        </div>
        <!-- Box 2 -->
        <div class="relative flex flex-col mt-24 p-6 space-y-6 bg-white rounded-lg md:w-1/3 md:mt-8">
            <!-- Image Positioning -->
            <div class="absolute -ml-10 left-1/2 -top-10 md:left-16">
                <!-- Image Container for Background & Center -->
                <div class="flex items-center justify-center w-20 h-20 p-4 rounded-full bg-veryDarkViolet">
                    <!-- Image -->
                    <img src="images/icon-detailed-records.svg" alt="">
                </div>
            </div>
            <h5 class="pt-6 text-xl font-bold text-center capitalize md:text-left">Detailed Records</h5>
            <p class="text-center text-gray-400md:text-left">
                Lorem ipsum dolor sit amet consectetur, adipisicing elit. In quibusdam ad dolore quae dolorum facilis eligendi delectus voluptates ipsam explicabo, pariatur eos distinctio! Doloribus maiores eos non esse aliquam fuga.
            </p>
        </div>
        <!-- Box 3 -->
        <div class="relative flex flex-col mt-24 p-6 space-y-6 bg-white rounded-lg md:w-1/3 md:mt-16">
            <!-- Image Positioning -->
            <div class="absolute -ml-10 left-1/2 -top-10 md:left-16">
                <!-- Image Container for Background & Center -->
                <div class="flex items-center justify-center w-20 h-20 p-4 rounded-full bg-veryDarkViolet">
                    <!-- Image -->
                    <img src="images/icon-fully-customizable.svg" alt="">
                </div>
            </div>
            <h5 class="pt-6 text-xl font-bold text-center capitalize md:text-left">Fully Customizable</h5>
            <p class="text-center text-gray-400md:text-left">
                Lorem ipsum dolor sit amet consectetur, adipisicing elit. In quibusdam ad dolore quae dolorum facilis eligendi delectus voluptates ipsam explicabo, pariatur eos distinctio! Doloribus maiores eos non esse aliquam fuga.
            </p>
        </div>
    </div>
</section>