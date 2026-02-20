<template>

<div id="tools" class="tech-marquee-wrapper">
    <div class="marquee-content">
        <div class="marquee-item"><img src="https://upload.wikimedia.org/wikipedia/commons/3/33/Figma-logo.svg" alt="Figma"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/a0aQ1YZ.png" alt="HTML 5"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/IqKJ2b3.png" alt="CSS 3"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/oYWXBMO.png" alt="Bootstrap 5"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/2ut8vqZ.png" alt="JavaScript"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/I9W3QrG.png" alt="MongoDB"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/asc8koI.png" alt="Express.js"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/2rERJyj.png" alt="React.js"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/0J58HCq.png" alt="Node.js"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/IZNwqnT.png" alt="Heroku"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/aLq73Jz.png" alt="Git"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/Tz0QsIs.png" alt="Postman"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/W9OXo8J.png" alt="Sublime Text"></div>

        <div class="marquee-item"><img src="https://upload.wikimedia.org/wikipedia/commons/3/33/Figma-logo.svg" alt="Figma"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/a0aQ1YZ.png" alt="HTML 5"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/IqKJ2b3.png" alt="CSS 3"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/oYWXBMO.png" alt="Bootstrap 5"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/2ut8vqZ.png" alt="JavaScript"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/I9W3QrG.png" alt="MongoDB"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/asc8koI.png" alt="Express.js"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/2rERJyj.png" alt="React.js"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/0J58HCq.png" alt="Node.js"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/IZNwqnT.png" alt="Heroku"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/aLq73Jz.png" alt="Git"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/Tz0QsIs.png" alt="Postman"></div>
        <div class="marquee-item"><img src="https://i.imgur.com/W9OXo8J.png" alt="Sublime Text"></div>
    </div>
</div>

</template>

<style scoped>

#tools {
    padding: 100px 0 110px; 
}
	
.tech-marquee-wrapper {
    overflow: hidden;
    width: 100%;
    background-color: #1a1f21;
    padding: 60px 0;
    /* Softens the edges to hide the 'entry' of logos */
    -webkit-mask-image: linear-gradient(to right, transparent, black 15%, black 85%, transparent);
    mask-image: linear-gradient(to right, transparent, black 15%, black 85%, transparent);
}

.marquee-content {
    display: flex;
    width: max-content; /* Forces the container to be as wide as all logos */
    flex-wrap: nowrap; 
    /* Direction: Left to Right */
    animation: scrollContinuous 25s linear infinite; 
}

.marquee-item {
    padding: 0 60px; /* Consistent spacing is key for the math to work */
    flex-shrink: 0;
}

.marquee-item img {
    height: 50px;
    filter: drop-shadow(0 4px 6px rgba(0,0,0,0.3));
}

/* THE SEAMLESS MATH */
@keyframes scrollContinuous {
    0% {
        /* Start with the first half already past the left edge */
        transform: translateX(-50%);
    }
    100% {
        /* Pull toward the right until the very beginning */
        transform: translateX(0);
    }
}
	
</style>