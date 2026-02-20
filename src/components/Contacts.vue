  <template>
  <div class="contact-section">
    <h1 class="text-center my-4 pt-3" id="contact">Contact</h1>
    <div class="container">
      <div class="row align-items-stretch mt-4 panel-card">
        <div class="col-md-6 map-container">
          <iframe
            id="gmap_canvas"
            src="https://maps.google.com/maps?q=centro%20escolar%20university%20manila&t=&z=13&ie=UTF8&iwloc=&output=embed"
            frameborder="0"
            scrolling="no"
            marginheight="0"
            marginwidth="0"
          ></iframe>
        </div>

        <div class="col-md-6 panel-form">
          <!-- binds the submitForm() function to the form submit event with @submit.prevent -->
          <form @submit.prevent="submitForm">
            <div class="mb-3">
              <!-- bind the "name" state to the form input v-model -->
              <input
                type="text"
                v-model="name"
                class="form-control contact-form-control"
                placeholder="First Name M.I. Last Name"
              />
            </div>

            <div class="mb-3">
              <input
                type="email"
                v-model="email"
                class="form-control contact-form-control"
                placeholder="Email"
              />
            </div>

            <div class="mb-3">
              <textarea
                v-model="message"
                class="form-control contact-form-control"
                rows="6"
                placeholder="Message"
              ></textarea>
            </div>

            <div class="form-footer">
              <div class="social-icons">
                <a href="https://www.linkedin.com/in/charles-babbage-8291a6211/" id="linkedin">
                  <i class="fab fa-linkedin"></i>
                </a>
                <a href="https://gitlab.com/cbabbage0991" id="gitlab">
                  <i class="fab fa-gitlab"></i>
                </a>
                <a href="https://github.com/cbabbage0991" id="github">
                  <i class="fab fa-github"></i>
                </a>
              </div>

              <!-- disable the button when sending -->
              <button type="submit" class="submit-btn" :disabled="isLoading">
                {{ isLoading ? "Sending..." : "Submit" }}
              </button>

              
              <div class="recaptcha-wrap">
                <div ref="recaptchaContainer"></div>
              </div>
            </div>
          </form>
        </div>

      </div>
    </div>
  </div>
</template>


<script setup>

import { ref, onMounted, onBeforeMount } from "vue";

import { Notyf } from "notyf";
import 'notyf/notyf.min.css';

const notyf = new Notyf();



const WEB3FORMS_ACCESS_KEY = "92c148aa-5e00-45a2-ab1e-f1f6a6e84be0";



const subject = "New message from Portfolio Contact Form";


const name = ref("");
const email = ref("");
const message = ref("");


const isLoading = ref(false);



const submitForm = async () => {

    
    if (!recaptchaToken.value) {
        notyf.error('Please verify that you are not a robot.');
        return;
    }

   
    isLoading.value = true;

    try {

        const response = await fetch("https://api.web3forms.com/submit", {
            method: "POST",
            headers: {
                "Content-Type": "application/json",
                Accept: "application/json",
            },
            body: JSON.stringify({
                access_key: WEB3FORMS_ACCESS_KEY,
                subject: subject,
                name: name.value,
                email: email.value,
                message: message.value,
            }),

        });

        const result = await response.json();

        
        if(result.success) {
            console.log(result);

            isLoading.value = false;
            notyf.success("Message Sent!");

          
            name.value = "";
            email.value = "";
            message.value = "";

        }

    } catch (error) {
        
        console.log(error);

        isLoading.value = false;
        notyf.error("Failed to send message. Please try again.");

    } finally {

        
        resetRecaptcha();
    }

}


const SITE_KEY = "6Lft_XEsAAAAAGK4IPcU7x0gSRcYx8wAF2ImZvkn"

const recaptchaContainer = ref(null);
const recaptchaWidgetId = ref(null);
const recaptchaToken = ref('');


// Once successfully verified the token will be stored in the recaptchaToken state variable.
function onRecaptchaSuccess(token) {
  recaptchaToken.value = token;
}

// Once the has been expired or is invalid.
function onRecaptchaExpired() {
  recaptchaToken.value = '';
}

// Renders the recaptcha component in our app.
function renderRecaptcha() {
  if (!window.grecaptcha) {
    console.error('reCAPTCHA not loaded');
    return;
  }

  recaptchaWidgetId.value = window.grecaptcha.render(recaptchaContainer.value, {
    sitekey: SITE_KEY,
    size: 'normal', // or 'compact'
    callback: onRecaptchaSuccess,
    'expired-callback': onRecaptchaExpired,
  });
}

// Function to reset reCaptcha
function resetRecaptcha() {
  if (recaptchaWidgetId.value !== null) {
    window.grecaptcha.reset(recaptchaWidgetId.value);
    recaptchaToken.value = '';
  }
}



onMounted(() => {

    const interval = setInterval(() => {

        if(window.grecaptcha && window.grecaptcha.render) {
            renderRecaptcha();
            clearInterval(interval);
        }

    },100);

    onBeforeMount(() => {
        clearInterval(interval);
    })
})


</script>


<style>


.contact-section {
  background-color: var(--primary-bg);
  padding: 50px 0 110px; 
}

.text-center {
  font-family: 'Archivo', sans-serif;
  font-weight: 900;
  letter-spacing: -3.px;
  color: #ffffff;
  padding: 50px;
}

.panel-card {
  background-color: var(--ui-box);
  border-radius: 22px;
  box-shadow: 0 26px 60px rgba(0, 0, 0, 0.35);
  overflow: hidden;
  position: relative;
}


.panel-card::after {
  content: "";
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 4px;
  background: var(--accent-gold);
  opacity: 0.65;
}


.map-container {
  padding: 0;
}

.map-container iframe {
  display: block;
  width: 100%;
  height: 100%;          
  min-height: 520px;    
  border: none;
}

.panel-form {
  padding: 44px 42px; 
  display: flex;
  flex-direction: column;
  justify-content: center;
}


.contact-form-control {
  background: transparent;
  border: 1px solid rgba(220, 215, 201, 0.18);
  color: var(--text-main);
  border-radius: 14px;
  padding: 14px 16px;
}

.contact-form-control::placeholder {
  color: rgba(245, 245, 245, 0.45);
}

.contact-form-control:focus {
  outline: none;
  box-shadow: none;
  border-color: rgba(162, 123, 92, 0.85);
}


.form-footer {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 20px;
  align-items: center;
  margin-top: 18px;
}

.social-icons {
  display: flex;
  gap: 16px;
}

.submit-btn {
  border-radius: 999px;
  font-weight: 700;
  padding: 12px 30px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.submit-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 16px 34px rgba(0, 0, 0, 0.35);
}

.submit-btn:disabled {
  opacity: 0.65;
}


.recaptcha-wrap {
  grid-column: 1 / -1;
  display: flex;
  justify-content: flex-end;
  padding-top: 10px;
}


@media (max-width: 991px) {
  .contact-section {
    padding: 80px 0;
  }

  /* ✅ make sure map has its own height and doesn't overflow */
  .map-container iframe {
    min-height: 240px;
    height: 240px;       /* ✅ fixed height on mobile */
  }

  .panel-form {
    padding: 32px 26px;
  }

  .form-footer {
    grid-template-columns: 1fr;
    gap: 16px;
  }

  .recaptcha-wrap {
    justify-content: flex-start;
  }
}

</style>