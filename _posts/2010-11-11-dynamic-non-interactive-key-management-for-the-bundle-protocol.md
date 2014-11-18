---
title: Dynamic, Non-Interactive Key Exchange for the Bundle Protocol
layout: post
summary: Summary of abstract on key exchange in DTNs.
tags: tech
---

<p>
<em>Note: This is an overview of a paper I published back in 2010. It has been backdated to reflect the time of its publication. The paper is found <a href="http://dl.acm.org/citation.cfm?id=1859951">here at the ACM website</a>.</em>
</p>

<h3>Background</h3>

<p>
From around 2008 until early 2011, much of my work revolved around the NASA-sponsored space DTN readiness effort.
This effort involves unifying all international civilian ground and space assets toward the creation of an "Interplanetary Internet".
The intention is to more highly optimize spacecraft mission operations by leveraging ad-hoc network links between spacecraft.
</p>

<p>
Within a delay/disruption tolerant network, there are constraints that many security mechanisms on the Internet cannot scale to meet.
For example, a key exchange protocol requiring a complex negotiation is impractical in environments with extreme latency or intermittent connectivity.
This motivates an investigation into novel approaches toward cryptographic key management that is appropriate for this class of networks.
In a space network involving spacecraft, ground stations, and mission-operations centers from a broad set of nations - with some member nations being suspicous of others - enabling security and trust in the network is critical to the success of the effort.
</p>

<p>
I presented this paper, suggesting a solution for cryptographic key exchange in a space DTN, at the <a href="http://dtnbone.umiacs.umd.edu/chants2010/">2010 ACM Workshop on Challenged Networks (CHANTS)</a> and it was subsequently published in the proceedings.
</p>

<h3>Foundations</h3>

<p>
The key-exchange solutions suggested in this paper rely on a relatively new domain in cryptography known as Pairing Based Cryptography.
It has the interesting property of enabling "identity-based" key establishment, in which an actor's public key is simply a hash of its public identity - for example, an e-mail address (though there are some global public parameters).
This is quite powerful, since it eliminates the need for a lengthy exchange of crpytographic information to produce shared secrets.
</p>

<p>
The protocols I proposed in my paper rely on the following properties of pairing-based cryptosystems and is conceptually very similar to the Diffie-Hellman key exchange over cyclic groups.
</p>

<p>
Take two suitable prime-order groups over elliptic curves, \(G_1\) and \(G_2\) and a bilinear function, \(e\) that maps two elements of \(G_1\) to a member of \(G_2\).
For all integers \(s \in [0, p-1]\), and \(X, Y \in G_1\) the following property holds.
</p>

<p>
$$s*e(X,Y) = e(s*X,Y) = e(X,s*Y))$$
</p>

<p>
This property can be leveraged for two parties to establish a distinct shared secret over a public channel without relying on any exchange.
Assume Alice and Bob are two parties wishing to exchange a secret, they are both bootstrapped with a secret value - a point on the elliptic curve \(G_1\).
This has been pre-computed by the group's authority and, in the case of Alice, is equal to \(S_A = s*H(Alice)\).
</p>

<p>
Alice wishes to encrypt a message to Bob, with whom she has never communicated before, so she takes his public identity, hashes it into a
point in the elliptic curve \(G_1\) as well as her pre-loaded secret \(S_A\), and computes

$$k = e(S_A, H(Bob))$$

Likewise, Bob, when he receives the message, computes 

$$k = e(S_B, H(Alice))$$

Due to the bilinearity of the function \(e\), these computations result to the same point in \(G_2\).
Thus, the two have shared a secret which can be the foundation of a symmetric cryptographic key.
A further property is that some other member of the group, Eve, cannot solve for the key between Alice and Bob.
Likewise, if a member of the group is compromised, or a shared secret between any two nodes in the network, all other pairwise shared secrets remain safe.
Furthermore, more nodes can be added to the network at any time and will inherently posses shared secrets with other nodes in the group.
This primitive is contingent on the difficulty of solving the discrete logarithm problem over elliptic curves.
</p>

<p>My suggestions for taking advantage of this primitive to enable non-interactive key exchange in the DTN Bundle Protocol security protocols are found in the <a href="http://dl.acm.org/citation.cfm?id=1859951">paper</a></p>

<br />
