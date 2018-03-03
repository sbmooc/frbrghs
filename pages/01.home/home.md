---
title: Home
mainimage: user/images/tomincafe.jpg
contact: true
bodyTitle: Good Things
bodyText: "Four Boroughs is a place to switch off from the material world - it’s minimal aesthetic and open vibe enables the focus to be on the good things on offer. The aim is to value the experience…both in the eating or drinking, and in appreciating the farmers, makers and brewers who don’t take shortcuts to produce the real, honest, good versions of things. \r\n\r\n Coffee beans are supplied by [Assembly](https://www.assemblycoffee.co.uk/) who are uncompromising in the beans they source from farmers around the globe before small batch roasting in Brixton. The House Espresso rotates with the seasons as do the selection of filter coffee beans for your home brews. Four Boroughs’ baristas are super diligent when it comes to getting a balanced extraction and letting the quality of the bean and roast shine through in every cup. \r\n\r\n For food and soft drink the norm is challenged. No sight of processed foods, drinks with excessive sugar and sweeteners or a reliance on animal produce – at Four Boroughs there are live cultures in the [kombucha](https://jarrkombucha.com/), [non-dairy kefir](https://www.purearth.co.uk/what-is-water-kefir/) and [kimchi](https://bottlebrushferments.com/) to promote gut health and all cakes are made refined-sugar free, gluten free and vegan by the [Conscientious Cook](http://www.theconscientiouscook.co.uk/).\r\n\r\n An affordable craft beer selection that is regularly changing sourced from a handful of London breweries is available to drink in or takeaway, and since opening in July, 2017, natural wine from [Under the Bonnet](http://www.winesutb.com/about) and [Les Caves de Pyrene](https://www.lescaves.co.uk/lescaves-home#home) and craft chocolate from [Cocoa Runners](https://cocoarunners.com/about-faqs/) has been added to the selection of good things.\r\n\r\n Open 7 days a week from 7am till 7pm. Available for private hire."

form:
    name: contact-form
    fields:
        - name: name
          label: Name
          placeholder: Enter your name
          autocomplete: on
          type: text
          validate:
            required: true

        - name: email
          label: Email
          placeholder: Enter your email address
          type: email
          validate:
            required: true
        - name: message
          label: Message
          placeholder: Enter your message
          type: textarea
          validate:
            required: true

    buttons:
        - type: submit
          value: Submit

    process:
        - email:
            from: "{{ config.plugins.email.from }}"
            to:
              - "{{ config.plugins.email.from }}"
              - "{{ form.value.email }}"
            subject: "[Feedback] {{ form.value.name|e }}"
            body: "{% include 'forms/data.html.twig' %}"
        - save:
            fileprefix: feedback-
            dateformat: Ymd-His-u
            extension: txt
            body: "{% include 'forms/data.txt.twig' %}"
        - message: Thank you for your feedback!
        - display: thankyou

---
