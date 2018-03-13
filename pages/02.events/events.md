---
title: Events
mainimage: tomincafe.jpg
contact: true
showliveEvents: true
showPreviousEvents: true
liveEvents:
    -
        eventTitle: 'Food vs Beer'
        eventSubtitle: 'The Seasonal Kitchen and Four Boroughs'
        eventDate: 'Fri 9th March'
        eventTime: '1930 – 2300'
        eventText: "Four Boroughs and Seasonal Kitchen are back for another round of 'food vs beer'. This will be an incredible evening of beer and food matching. You will have four plant-based courses and four beers. Carefully matched after in depth testing (I know we have a difficult job!). \r\n\r\nBoth teams from Four Borough’s and Seasonal Kitchen will be on hand to talk you through the beer & food pairings."
        eventPhoto: foodvsbeer.jpg
        eventLink: 'https://www.eventbrite.co.uk/e/food-vs-beer-with-the-seasonal-kitchen-and-four-boroughs-tickets-42421080594'
        eventSoldOut: false
previousEvents:
    -
        eventTitle: 'GOOD VINS'
        eventDate: '15th Feb'
        eventTime: '7.45pm - 10pm'
        eventText: 'We will have a selection of five GOOD VINS to taste curated by the guys behind 161 Kirkdale and Under the Bonnet Wines...this means they will be wines that have had minimal technological and chemical intervention, rather they are made in the same way as everything else in Four Boroughs...by master crafts people relying on the investment of time, effort and experience.'
        eventPhoto: goodvins.jpg
showLiveEvents: true
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
                    - '{{ config.plugins.email.from }}'
                    - '{{ form.value.email }}'
                subject: '[Feedback] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: feedback-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            message: 'Thank you for your feedback!'
        -
            display: thankyou
---

