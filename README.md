# Monetization

We have photographs, but what we really want is artwork - by Monet. So we Monetize the photographs.

The dataset and challenge come from a Kaggle competition, where 300 Monet paintings and 7038 photos are made available in jpeg format.
The challenge is to build a GAN (Generative Adversarial Network) to transform the pictures into Monet-like "paintings".

How do we do this?
- Create a network (the Generator) that makes Monet-like images from both photos and Monets;
- Create a network (discriminator - the Adversary) that evaluates whether a real Monet or a Monetized photo is in fact a Monet;
- Track loss on discriminator through comparison with ideal output: all-ones for real Monets, all-zeros for Monetized photos;
- Track loss on generator by comparing real Monet with Monet generated from real Monet and by including discriminator loss on Monetized photos.

Essentially: as the Adversary judges how bad generated Monets are, the Generator learns to make better Monets.
