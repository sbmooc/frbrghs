---
title: Home
mainimage: 180211_Four-Boroughs_45.jpg
headerTitle: 'FOUR <br> BOROUGHS'
headertitleclass: darkheader
headerbackground: true
contact: true
bodyTitle: 'GOOD THINGS'
bodyText: "Four Boroughs is a place to switch off from the material world - it’s minimal aesthetic and open vibe enables the focus to be on the good things on offer. \r\n\r\nCoffee beans are small batch roasted by [Assembly](https://www.assemblycoffee.co.uk/) in Brixton who knock out sweet, delicious beans time after time. The House Espresso rotates with the seasons as do the selection of filter coffee beans for your home brews. Four Boroughs’ baristas are super diligent when it comes to getting a balanced extraction and letting the quality of the bean and roast shine through in every cup. \r\n\r\n For food and soft drink the norm is challenged. There are live cultures in the [kombucha](https://jarrkombucha.com/), [non-dairy kefir](https://www.purearth.co.uk/what-is-water-kefir/) and [kimchi](https://bottlebrushferments.com/) to promote gut health and all cakes are made refined-sugar free, gluten free and vegan by the [Conscientious Cook](http://www.theconscientiouscook.co.uk/).\r\n\r\n An affordable craft beer selection that is regularly changing sourced from a handful of London breweries is available to drink in or takeaway, as is natural wine from [Under the Bonnet](http://www.winesutb.com/about) and [Les Caves de Pyrene](https://www.lescaves.co.uk/lescaves-home#home). Craft chocolate from [Cocoa Runners](https://cocoarunners.com/about-faqs/) opens up a whole other world.\r\n\r\n Open 7 days a week from 7am till 7pm. Available for private hire."
headerimageclass: darkheader
headerTitleColor: pinkheader
headerTitleBackground: false
bodySubtitle: "coffee. beer. kombucha. natural wine \r\n\r\n 7 - 7 Everyday"
form:
    name: contact-form
    fields:
        -
            name: name
            label: Name
            placeholder: 'Enter your name'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        -
            name: email
            label: Email
            placeholder: 'Enter your email address'
            type: email
            validate:
                required: true
        -
            name: message
            label: Message
            placeholder: 'Enter your message'
            type: textarea
            validate:
                required: true
    buttons:
        -
            type: submit
            value: Submit
    process:
        -
            email:
                from: '{{ config.plugins.email.from }}'
                to:
                    - '{{ config.plugins.email.to }}'
                    - '{{ form.value.email }}'
                subject: '[Form Submission] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: feedback-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            message: 'Thanks for your message - we''ll be in touch'
        -
            display: /home/thankyou
custom_file:
    user/images/180211_Four-Boroughs_45.jpg:
        name: 180211_Four-Boroughs_45.jpg
        type: image/jpeg
        size: 667579
        path: user/images/180211_Four-Boroughs_45.jpg
---

