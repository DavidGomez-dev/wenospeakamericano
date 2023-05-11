---
title: "Thank you for reading We No Speak Americano | Book to emigrate to United States"
layout: splash
lang: en-US
ref: landingbook
---

<div class="flex-container">
  <div class="text-container" markdown="1">
# Thank you very much for reading our book!
  </div>
  <div class="image-container">
    <img src="/assets/images/usa.gif" alt="Placeholder Image">
  </div>
</div>

### Please share it in any of this social networks and download a free summary for the VISAS

<div class="shareBtnCard">
  <div class="button-container">
    <button class="button btn btn--large shareBtn shareOnTwitter">
      Share in Twitter <i class="fab fa-twitter"></i>
    </button>
    <button class="button btn btn--large shareBtn shareOnLinkedIn">
      Share in Linkedin <i class="fab fa-linkedin-in"></i>
    </button>
    <button class="button btn btn--large shareBtn shareOnInstagram">
      Share in Facebook <i class="fab fa-facebook"></i>
    </button>
    <button class="button btn btn--large shareBtn shareOnWhat">
      Share in WhatsApp <i class="fab fa-whatsapp"></i>
    </button>
  </div>
  <div class="button-container">
    <button class="button btn btn--large btn--inverse" id="downBtn" disabled>Share first to download 👆</button>
  </div>
</div>

<br />

### Do you want to know more?

[Visit the official blog](/wenospeakamericano/blog/)

{% assign entries_layout = 'grid' %}

{% assign sitepostslang = site.posts | where: "lang", page.lang %}

<div class="entries-{{ entries_layout }}">
  {% for post in sitepostslang  limit:8 %}
    {% include archive-single.html type=entries_layout %}
  {% endfor %}
</div>

<script type="text/javascript">
  document.addEventListener(
    "DOMContentLoaded",
    function () {
      const shareBtns = document.querySelectorAll(".shareBtn");
      const downloadBtn = document.getElementById("downBtn");
      const button1 = document.querySelector(".shareOnTwitter");
      const button2 = document.querySelector(".shareOnLinkedIn");
      const button3 = document.querySelector(".shareOnInstagram");
      const button4 = document.querySelector(".shareOnWhat");

      shareBtns.forEach((btn) => {
        btn.addEventListener("click", (e) => {
          e.preventDefault();
          downloadBtn.innerHTML = 'Checking if link has been shared... <i class="fas fa-spinner fa-spin"></i>';
          setTimeout(() => {
            downloadBtn.disabled = false;
            downloadBtn.innerHTML = "Download free VISA Guide";
            downloadBtn.classList.remove("btn--inverse");
            downloadBtn.classList.add("btn--primary");
          }, 10000);
        });
      });

      const message = encodeURIComponent(
        "I have just read this book for studying, working or living in the US. I recommend it!! #immigration #US #H1B"
      );
      const shareUrl = encodeURIComponent("https://www.amazon.com/dp/B0C2SFPMS4?maas=maas_adg_AFB58EE4A84ACF0642385545DB24A3AD_afap_abs&ref_=aa_maas&tag=maas");

      // function to share a message on Twitter
      function shareOnTwitter() {
        //const message = encodeURIComponent("Hello Twitter!");
        const handle = " @WeNoSpeak_Book";
        const url = `https://twitter.com/intent/tweet?text=${message + handle}&url=${shareUrl}`;
        window.open(url, "_blank");
      }

      // function to share a message on LinkedIn
      function shareOnLinkedIn() {
        //const message = encodeURIComponent("Hello LinkedIn!");
        //const url = `https://www.linkedin.com/shareArticle?mini=true&url=${shareUrl}&title=&summary=&source=&text=${message}`;

        // const url =
        //   "https://www.linkedin.com/shareArticle?mini=true&url=" +
        //   shareUrl +
        //   "&title='I recommend this book for USA'&summary=" +
        //   message +
        //   "&source=";
        const url = `https://www.linkedin.com/sharing/share-offsite/?url=${shareUrl}`;
        window.open(url, "_blank");
      }

      // function to share a message on Instagram
      function shareOnInstagram() {
        //const message = encodeURIComponent("Hello Instagram!");
        const url = `https://www.facebook.com/sharer/sharer.php?u=${shareUrl}`;
        window.open(url, "_blank");
      }

      // function to share a message on Whatsapp
      function shareOnWhat() {
        //const message = encodeURIComponent("Hello Instagram!");
        const url = `whatsapp://send?text=${message} ${shareUrl}`;
        window.open(url, "_blank");
      }

      // function to download a PDF
      function downloadPDF() {
        //TODO to change link
        const url = "https://www.wenospeakamericano.com/assets/doc/visa-guide-eng.pdf";
        const link = document.createElement("a");
        link.href = url;
        link.setAttribute("download", "");
        link.click();
      }

      // attach event listeners to buttons 1, 2, and 3
      button1.addEventListener("click", shareOnTwitter);
      button2.addEventListener("click", shareOnLinkedIn);
      button3.addEventListener("click", shareOnInstagram);
      button4.addEventListener("click", shareOnWhat);
      downloadBtn.addEventListener("click", downloadPDF);
    },
    false
  );
</script>
