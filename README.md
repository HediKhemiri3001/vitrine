# Vitrine

This presents the front end for the Vitrine application.

## Main goal and Todos:

**Main goal:**
This project consists of a website regrouping all small artists and producers to be able to give them a centralised platform, where they can sell their products.
This would help them evolve and give them more visibility and exposure, and rid them of the need for creating and maintaining social media accounts for their brands, and as such have them focus on the quality of their product and art.

**TODOS**

- [ ] Design the website and all media assets.
- [ ] Start implementing the design.
- [ ] Envision the back architecture with deployment plans and testing.
- [ ] Discuss payment methods and consider the many options avalaible for Tunisian market first, international market second.

# Back planning:

In this section we will discuss expected back end functionalities just to make the product vision clear.
Main features:

- Catalog browsing.
- Cart functionality.
- Authentication and registration. (So logically account settings page)
- Payment API (using ClickToPay)
- Brand owner interface, includes sales metrics, stats and ability of product addition.

Notes :

- such make it possible to implement the purchasing history feature, this can be of help for brand owners so they have more data about their buyers such as their countries, to be able to build product strategies around this point.

Basic usage scenario:

- When a user visits the website, he has the possibility to browse the catalog of products, he can then add products to cart and checkout, not that the checkout process needs the user to be logged in.
- When a brand owner connects, a button that takes him to the brand owner interface appears.

Entities so far:

```
Product{
    name: string
    quantity: number
    maker: Brand /* ManyToOne */
    price: float
    discount: float
    pictures: Url[]
}
User{
    firstname: string
    lastname: string
    email: string
    phonenumber: string
    password: string
    history: PurchaseHistory[]
}
Client extends User{
    history: PurchaseHistory[]
    may_like: Tag[]
}
Owner extends User{
    brand: Brand
}
Brand{
    name: string
    logo: Url
    owner: User
    products: Products[]
}
```

- Users
-
