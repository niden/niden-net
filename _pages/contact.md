---
layout: page
title: Contact
permalink: /contact
---

<p class="m-b-30">
    If you have a project you would like to discuss, get in touch with me. I 
    would be happy to help you find the best solution for your needs.
</p>
<!-- begin row -->
<div class="row row-space-30">
    <!-- begin col-12 -->
    <div class="col-md">
        <form class="form-horizontal" 
              name="niden-net-contact" 
              method="post"
              data-netlify="true" 
              data-netlify-recaptcha="true">
            <div style="display: none;">
                <label>
                    Don't fill this out if you’re human:
                    <input name="bot-field" />
                </label>
            </div>
            <div class="mb-3 row">
                <label class="col-form-label col-md-3 text-md-right">
                    Name <span class="text-danger">*</span>
                </label>
                <div class="col-md-9">
                    <input type="text" class="form-control">
                </div>
            </div>
            <div class="mb-3 row">
                <label class="col-form-label col-md-3 text-md-right">
                    Email <span class="text-danger">*</span>
                </label>
                <div class="col-md-9">
                    <input type="text" class="form-control">
                </div>
            </div>
            <div class="mb-3 row">
                <label class="col-form-label col-md-3 text-md-right">
                    Message <span class="text-danger">*</span>
                </label>
                <div class="col-md-9">
                    <textarea class="form-control" rows="10"></textarea>
                </div>
            </div>
            <div class="mb-3 row">
                <label class="col-form-label col-md-3 text-md-right">
                </label>
                <div class="col-md-9">
                    <div data-netlify-recaptcha="true"></div>
                </div>
            </div>
            <div class="mb-3 row">
                <label class="col-form-label col-md-3 text-md-right"></label>
                <div class="col-md-9 text-left">
                    <button type="submit" class="btn btn-dark btn-lg btn-block">
                        Send Message
                    </button>
                </div>
            </div>
        </form>
    </div>
    <!-- end col-8 -->
</div>
<!-- end row -->

<script type="application/javascript">
    const handleSubmit = (event) => {
        event.preventDefault();

        const myForm = event.target;
        const formData = new FormData(myForm);
        var payload = {
            method: "POST",
            headers: { "Content-Type": "application/x-www-form-urlencoded" },
            body: new URLSearchParams(formData).toString(),
        };

        fetch("/", payload)
            .then(() => {
                alert("Thank you for your query. We will get back to you shortly.");
                window.location.reload();
            })
            .catch((error) => alert(error));
    };

    document
        .querySelector("form")
        .addEventListener("submit", handleSubmit);
</script>