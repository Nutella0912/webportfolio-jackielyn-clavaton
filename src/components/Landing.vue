<template>
	
<section id="home" class="hero-section d-flex align-items-center">
    <div class="container">
        <div class="row align-items-center justify-content-between">
            
            <div class="col py-5">
                <h1 class="hero-title mt-3">
                    HAY! I'M JACKIELYN <br>
                    <span class="text-accent">I'M A WEB DEVELOPER</span>
                </h1>
                <p class="text-muted-custom mt-4" id="description">
                    I focus on precision, scalability, and modern user experiences. 
                    Building clean, functional digital experiences from design to logic.
                </p>
                
                <div class="hero-action-row mt-5">
                    <a href="#contact" class="btn-outline-custom">GET IN TOUCH —&gt;</a>
                    <div class="hero-dots d-inline-flex ms-4">
                        <span class="dot"></span>
                        <span class="dot"></span>
                        <span class="dot"></span>
                    </div>
                </div>
            </div>

            
        </div>
    </div>
</section>

</template>

<style scoped>
	
.hero-section {
    background-color: #2C3639; 
    min-height: 90vh; 
    padding: 100px 0;
}


.hero-title {
    font-family: 'Archivo', sans-serif;
    font-weight: 900;
    font-size: clamp(3rem, 8vw, 5rem); 
    line-height: 1;
    color: #FFFFFF;
    letter-spacing: -2px;
    text-transform: uppercase;
}
#description {
    color: #FFFFFF;
}

.text-accent {
    color: var(--accent-gold); 
}
.hero-img-box img {
    border-radius: 40px 40px 200px 200px; 
    box-shadow: 0 50px 100px rgba(0,0,0,0.6);
    background-color: #3F4E4F; 
    border: 1px solid rgba(255,255,255,0.05);
}

.btn-outline-custom {
    color: #DCD7C9;
    border: 1.5px solid #ffffff;
    padding: 12px 28px;
    text-decoration: none;
    font-weight: 700;
    font-size: 0.85rem;
    text-transform: uppercase;
    transition: 0.3s ease;
}

.btn-outline-custom:hover {
    background-color: var(--accent-gold);
    color: #ffffff;
}

.dot {
    width: 10px;
    height: 10px;
    background: #ffffff;
    border-radius: 50%;
    margin: 0 4px;
    opacity: 0.2;
}
</style>