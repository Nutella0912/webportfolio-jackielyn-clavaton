<template>
	
<section id="footer" class="footer-section py-5">
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-lg-8 text-center">
                
                <h1 class="display-4 fw-black mt-3">
                    WHY <span class="text-accent">ME?</span>
                </h1>

                <p class="text-muted-custom mx-auto mt-3" style="white-space: normal;">
                    Whether it's design or strategy, I bring a unique perspective to every project. I focus on precision, scalability, and modern user experiences.
                </p>

                <div class="socia-wrapper mt-5">
                    <a href="https://www.facebook.com/jackielyn.clavaton.7" class="social-circle"><img src="/images/Social/facebook.png" alt="Facebook"></a>
                    <a href="https://www.linkedin.com/in/jackielyn-clavaton-21911118a/" class="social-circle"><img src="/images/Social/linkedin.png" alt="LinkedIn"></a>
                    <a href="https://www.instagram.com/jackielynclavaton/" class="social-circle"><img src="/images/Social/instagram.png" alt="Instagram"></a>
                    <a href="mailto:jackielyn.clavaton@gmail.com"class="social-circle"><img src="/images/Social/email.png" alt="Email"></a>
                    <a href="https://discord.com/users/1447129360329871391" class="social-circle"><img src="/images/Social/discord.png" alt="Discord"></a>
                    <a href="https://web.whatsapp.com/" class="social-circle"><img src="/images/Social/social.png" alt="WhatsApp"></a>
                    <a href="viber://chat?number=%2B639388904567" class="social-circle" title="+63 938 890 4567" aria-label="Contact via Viber"><img src="/images/Social/viber.png" alt="Viber"></a>
                </div>
            </div>
        </div>
    </div>
</section>

</template>

<style>

.footer-section {
    background-color: var(--primary-bg); /* #2C3639 */
    padding: 100px 0;
    text-align: center;
}

/* Heading Style */
.footer-section h1 {
    font-family: 'Archivo', sans-serif;
    font-weight: 900;
    letter-spacing: -1.5px;
    color: #ffffff;
}

/* Prevent the header letters from overlapping */
.fw-black {
    font-weight: 900;
    letter-spacing: 0.02em; /* Adds a tiny bit of breathing room */
}

/* Fix the squashed paragraph text */
.text-muted-custom {
    letter-spacing: normal;
    word-spacing: normal;
    line-height: 1.6; /* Improves readability */
    display: block;   /* Ensures it takes up full width */
    max-width: 600px; /* Prevents it from getting too wide/thin */
}


/* Social Wrapper Grid */
.socia-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 15px;
    flex-wrap: wrap;
}

/* The Circular Bubble */
.social-circle {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 55px;
    height: 55px;
    background-color: var(--ui-box); /* #3F4E4F */
    border-radius: 50%;
    transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    text-decoration: none;
}

/* Icon size inside bubble */
.social-circle img {
    width: 24px;
    height: auto;
    filter: brightness(1);
}

/* Hover Effect: Glow and Pop */
.social-circle:hover {
    background-color: var(--accent-gold);
    transform: translateY(-8px);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
}

.social-circle:hover img {
    filter: brightness(0) invert(1); /* Turns icon white on hover */
}

</style>