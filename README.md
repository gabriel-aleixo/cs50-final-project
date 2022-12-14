# PizzaVision

> We bought the same bad frozen pizza twice... π
> Never again! π₯Άππ - **Me**

> As the pizza nourishes the body, so too does wisdom nourish the mind. Just as the body cannot thrive without proper sustenance, the mind cannot thrive without wisdom. Therefore, let us nourish our minds with the wisdom of the Dhamma, and our bodies with the nourishing sustenance of pizza. - **GPT-3 on the importance of eating pizza**

## Introduction

PizzaVision is a mobile app that lets you take pictures of the packages of the frozen pizza you buy, and tag them as either "π" or "π".

The next time you are buying frozen pizza and you can't remember if you already had or liked that particular type - a surprisingly common problem! - just take snapshot of the box and the app will show you if you tagged it in the past.

### Video Demo: [PizzaVision Video Demo](https://youtu.be/UvWqgWUDMGE)

### Live Demo: [pizzavision.onrender.com](https://pizzavision.onrender.com/)

### Description

There are way too many varieties of frozen pizza in your average grocery store. They usually all look the same, with their italian-sounding names, their nice pictures of red ripe tomatoes, fresh basil, and melted cheese.

However, they most certainly do not taste the same! We know good frozen pizza from bad frozen pizza when we eat it, right?

But how can we remember and keep track of the ones we bought before and liked, versus the ones we should steer away from?

I built PizzaVision to solve this fundamental problem.

You simply take a snapshot of a pizza's box and select "π" or "π" (same as "Yes" or "No", but different) to indicate whether you would buy it again or not.

The next time you're in the supermarket, and you can't remember if you had that particular forzen pizza before, just take a snapshot of the package and the app will show you all the similar pizzas you had, which were Yesses, and which were Noes.

### Background

This is my final project for the Harvard CS50x course. I wanted to build something that would allow me to learn and use new technologies, go through all the step of planning, designing and building a product, and at the same, tackle a consequential and meaningful challenge affecting the lives of many people.

That last part ended up meaning tackling a funny and silly problem affecting the lives of at least two people, my wife and I. But that seems good enough for me!

#### So many frozen pizzas π¨

It may seem silly, but it's very hard to keep track of all the different brands and types of frozen pizza we eat. More often than we liked, we ended up buyiong the same brand just to realise that we had it before and it wasn't that great. Something needed to be done about it!

#### Scrambling through imperfect methods

We started by creating a shared album on Google Photos. We'd take a picture with our phones, manually write Yes or No on to of it, and add to the album.

Can you believe the amount of work??! Not to mention that finding a specific product in this album was nightmare... 

We thought about keeping a list with the brands, names, etc. This would be easy to search and share, but again, so much work...

We just wanted an easy way to remember and quickly check the products we liked, particularly at the supermarket.

#### Only Pizza, really?

Well, I guess you _could_ use the app for other products, such as wine bottles, beer, coffee, or any other packaged product, really. But why _would_ you do that, when there are so many other more complicated apps to do basically the same thing?

Besides, if you don't have your pizza game in order, you shouldn't be worrying about unimportant things like coffe or beer. First things first!

## Installation

TODO

## Specifications

### Tech Stack

#### Frontend

- [Ionic](https://ionicframework.com/docs/react): cross-platform mature framework, large community support, many available plugins to interact with mobile platform features, UI components built in, familiar development experience using HTML, CSS and JavaScript.
- [Capacitor](https://capacitorjs.com/docs): the cross-platform runtime on top of which the Ionic app runs. Capacitor is mainly providing access to filesystem, camera and localstorage for the app.
- React: well supported and integrated with Ionic, extremely mature and popular.
- [@tensorflow/tfjs](https://www.tensorflow.org/js/tutorials/setup?hl=en) with the [@tensorflow-models/mobilenet](https://www.npmjs.com/package/@tensorflow-models/mobilenet) for the computer vision bits. [Mobilenet](https://github.com/tensorflow/tfjs-models/tree/master/mobilenet) is a small, low-latency and low-power model that can extract embeddings and and provide image classification. It is particularly adapted for use in mobile apps, and it is providing image vectors in this app, which are used to calculate image similarity.
- Thanks to this simple Cosine Similarity function by [Tomer Gabbai](https://gist.github.com/tomericco/14b5ceac90d6eed6f9ba6cb5305f8fab), we estimate image similarity on the fly. In the future, I would be straightforward to let the user select the sensitivity of the similarity results they see.

#### Backend

- [Supabase](https://supabase.com/docs): relational database (PostgreSQL), Auth, object storage, basic CRUD API, realtime API (which is really cool). Very easy to set-up, growing community, based on open source software, strong row-level security built-in, free tier available. I'm also leveraging Supabase Storage to sync the user's pictures to the cloud. This way, if you uninstall the app, your data is kept in the cloud.

### Features

- User authentication via one time password with phone number
- Basic user profile management (name, website)
- Take pictures with your phone's camera
- Upload picture from your phone's photo library
- Tag a picture as π or π
- Tap an existing picture to change its tag or remove from the library
- Display all similar images for the selected picture. Results ordered by image similarity
- Libray view ordered by date taken
- Filter library by π and π tags
- Sync local images with cloud

## TODO

- Implement infinite scroll on the home feed
- Add account management options: change email, delete account

## FAQs

TODO

## References

- https://ionicframework.com/docs/react/your-first-app
- https://github.com/tensorflow/tfjs-models/tree/master/mobilenet

- https://blog.devgenius.io/mobile-development-with-react-native-or-ionic-a9ea855749f6
- https://towardsdatascience.com/image-similarity-with-deep-learning-c17d83068f59

- https://supabase.com/docs/guides/with-ionic-react
- https://ionic.io/blog/choosing-a-data-storage-solution-ionic-storage-capacitor-storage-sqlite-or-ionic-secure-storage
