---
title: Events
mainimage: user/images/tomincafe.jpg
contact: true
events:
  -
      eventTitle: "Food vs Beer \r\n\r\n ### The Seasonal Kitchen and Four Boroughs"
      eventDate: Fri 9th March
      eventTime: 1930 – 2300
      eventPrice: £47.75
      eventText: "Four Boroughs and Seasonal Kitchen are back for another round of 'food vs beer'. This will be an incredible evening of beer and food matching. You will have four plant-based courses and four beers. Carefully matched after in depth testing (I know we have a difficult job!). \r\n\r\nBoth teams from Four Borough’s and Seasonal Kitchen will be on hand to talk you through the beer & food pairings."
      eventPhoto: https://img.evbuc.com/https%3A%2F%2Fcdn.evbuc.com%2Fimages%2F39901900%2F241986704004%2F1%2Foriginal.jpg?w=800&rect=0%2C204%2C1632%2C816&s=f529271a623d5a13d9fe4df3cc7f6ac3
      eventLink: https://www.eventbrite.co.uk/e/food-vs-beer-with-the-seasonal-kitchen-and-four-boroughs-tickets-42421080594
      eventSoldOut: false

avaliableForHireTitle:
avaliableForHireText:

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
