<template>
	
	<!-- navbar starts -->
	<nav class="navbar fixed-top navbar-expand-lg">
	    <div class="container">
	        <a class="navbar-brand" href="#">jackielyn</a>
	        <button
	          class="navbar-toggler"
	          type="button"
	          data-bs-toggle="collapse"
	          data-bs-target="#navbarNav"
	          aria-controls="navbarNav"
	          aria-expanded="false"
	          aria-label="Toggle navigation"
	        >
	          <span class="navbar-toggler-icon"></span>
	        </button>
	        <div class="collapse navbar-collapse" id="navbarNav">
	            <div class="navbar-nav ms-auto"> <a class="nav-link active" href="#">Home</a>
	                <a class="nav-link" href="#tools">Tools</a>
	                <a class="nav-link" href="#about">About</a>
	                <a class="nav-link" href="#projects">Projects</a>
	                <a class="nav-link" href="#contact">Contact</a>
	            </div>
	        </div>
	    </div>
	</nav>
	<!-- navbar end -->


</template>

<style scoped>

.navbar {
    background-color: #1E2629 !important; 
    padding: 0.1rem 0; 
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.navbar-brand {
    color: var(--secondary-bg) !important; 
    font-size: 1.5rem;
}

.navbar-nav .nav-link {
    color: #FDFFF4 !important;
    margin-left: 25px;
    font-size: 0.9rem;
    font-weight: 600; 
    text-transform: uppercase;
    transition: 0.3s ease;
}

.navbar-nav .nav-link:hover {
    color: var(--accent-gold) !important; 
}
.navbar-toggler {
  border-color: rgba(255,255,255,0.2);
}
.navbar-toggler-icon {
  filter: invert(1); 
}
	
</style>