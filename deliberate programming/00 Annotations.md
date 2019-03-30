# Annotations
## Analysis
### Commit [2dd](https://github.com/deliberate-programming/text_layout/commit/2dda949faf23137dff9f0b5cf4a21241a0bee747)
Trying to get a grip on the data structure. A text is not just a blob. It's a hierarchy which needs to be rearranged.

### [0ea](https://github.com/deliberate-programming/text_layout/commit/0ea238d83d6cc8b6be4b50296a7558e52da3b4b8)
Extracting some domain language from the requirements. Not just terms, but terms in context. I'm asking myself: "What's going on?"

### [bc5](https://github.com/deliberate-programming/text_layout/commit/bc5f953868a3a85ae010c9906e8ba73664c82ae3), [644](https://github.com/deliberate-programming/text_layout/commit/644e46ccf4f4f8898fd45c6d860d0037b4fc514d)
Even though there are a couple of examples in the requirements I'm writing up some for myself. That way I can focus more on specific aspects. (If there was a PO I could talk to, I'd show them to her.)

### [05b](https://github.com/deliberate-programming/text_layout/commit/05b04ed4a36ca2a728e20a8f15b62c1c221b7fcf)
The requirements are not huge, but still I don't feel well about implementing them all in one go without intermediate feedback.

Also I learned in the past DP exercise to progress in smaller steps. There's an opportunity to do so here. The problem lends itself to incremental development: input data can start simple and become more and more elaborate all going through the same function.

### [6d5](https://github.com/deliberate-programming/text_layout/commit/6d5ee3f57fa5229f4da803d8761312738c468b9d)
The function to put under acceptance test is simple. I decide to encode the source/destination text as `string`. The function will do all necessary parsing. No need for a client to deliver lines or some other data structure.