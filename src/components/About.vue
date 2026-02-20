<template>
	
<section id="about" class="about-section">
    <div class="container">
        <div class="row align-items-center">

            <div class="col-lg-5 mb-4 mb-lg-0">
                <div class="about-image">
                    <img src="/images/Others/jack.jpg" alt="Jackielyn" class="img-fluid custom-img">
                </div>
            </div>

            <div class="col-lg-7 ps-lg-5">
                <span class="badge-text">JACKIELYN CLAVATON</span>


                
                <h2 class="display-5 fw-bold mt-3 text-white">
                    I AM AVAILABLE FOR <span class="text-accent">CUSTOM SOFTWARE & WEB SOLUTIONS</span> PROJECT
                </h2>
                
                <p class="mt-4 text-muted-custom">
                    Building the Full Stack, Refining the User Experience.
                </p>

                <div class="d-flex mt-4 gap-3 stats-container">
                    <div class="stat-box">
                        <h3>100%</h3>
                        <p>Success rate</p>
                    </div>
                    <div class="stat-box">
                        <h3>Modern</h3>
                        <p>Tech Stack</p>
                    </div>
                    <div class="stat-box">
                        <h3>24/7</h3>
                        <p>Dedicated Support</p>
                    </div>
                </div>
                
                <div class="mt-5">
                    <a href="#" class="btn-message">MESSAGE NOW</a>
                </div>
            </div>

        </div> 
    </div>
</section>

</template>

<style scoped>

.about-section {
    background-color: var(--primary-bg) !important; 
    color: #ffffff;
    padding: 150px 0 100px 0; 
}


.about-section h2 {
    font-family: 'Archivo', sans-serif; /* Match the landing page font */
    font-weight: 900;
    font-size: 3.5rem; /* Large enough to remove the 'empty' feeling */
    line-height: 1.1;
    letter-spacing: -1.5px;
}

.about-section h2 span {
    color: #DCD7C9; /* Champagne for better readability */
    text-shadow: 0 0 10px rgba(220, 215, 201, 0.2);
}

.badge-text {
    background: var(--ui-box); 
    color: var(--secondary-bg);
    padding: 6px 14px;
    border-radius: 4px;
    font-size: 0.7rem;
    font-weight: 600;
    text-transform: uppercase;
}

.custom-img {
    border-radius: 40px; /* Slightly larger for a more modern look */
    box-shadow: 0 40px 80px rgba(0, 0, 0, 0.6); /* Deeper shadow creates depth */
    width: 100%;
    display: block;
    transition: transform 0.3s ease; /* Adds a nice feel when hovering */
}

.text-accent {
    color: var(--accent-gold); 
}


/* --- 5. STAT BOXES FIX --- */
.stat-box {
    background: var(--ui-box); 
    padding: 25px 20px;
    border-radius: 12px;
    flex: 1;
    min-width: 140px;
    text-align: left;
    border-bottom: 4px solid var(--accent-gold);
    transition: transform 0.3s ease;
}

.stat-box h3 {
    font-family: 'Archivo', sans-serif;
    font-weight: 900;
    font-size: 1.8rem;
    color: #ffffff; /* Pure white for the numbers */
    margin-bottom: 2px;
}

.stat-box p {
    font-family: 'Inter', sans-serif;
    /* High-contrast champagne color so it's actually visible */
    color: var(--secondary-bg) !important; 
    font-weight: 600;
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 1.2px;
    margin: 0;
    opacity: 1; /* Ensures no transparency is hiding the text */
}

/* --- 6. BUTTONS --- */
.btn-message {
    display: inline-block;
    padding: 12px 35px;
    border: 2px solid var(--accent-gold);
    color: var(--accent-gold);
    text-decoration: none;
    font-weight: 700;
    text-transform: uppercase;
    border-radius: 6px;
    transition: 0.3s ease;
}

.btn-message:hover {
    background-color: var(--accent-gold);
    color: #ffffff;
}


</style>