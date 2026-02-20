<template>
	
<section id="footer" class="footer-section py-5">
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-lg-8 text-center">
                
                <h1 class="display-4 fw-black mt-3">
                    WHY <span class="text-accent">ME?</span>
                </h1>
                
                <p class="text-muted-custom mx-auto mt-3">
                    Whether it's design or strategy, I bring a unique perspective to every project. 
                    I focus on precision, scalability, and modern user experiences.
                </p>

                <div class="socia-wrapper mt-5">
                    <a href="#" class="social-circle"><img src="/images/Social/facebook.png" alt="Facebook"></a>
                    <a href="#" class="social-circle"><img src="/images/Social/linkedin.png" alt="LinkedIn"></a>
                    <a href="#" class="social-circle"><img src="/images/Social/instagram.png" alt="Instagram"></a>
                    <a href="#" class="social-circle"><img src="/images/Social/email.png" alt="Email"></a>
                    <a href="#" class="social-circle"><img src="/images/Social/discord.png" alt="Discord"></a>
                    <a href="#" class="social-circle"><img src="/images/Social/social.png" alt="WhatsApp"></a>
                    <a href="#" class="social-circle"><img src="/images/Social/viber.png" alt="Viber"></a>
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