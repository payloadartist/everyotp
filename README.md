# EveryOTP: Your Secrets, Our Certainty.

**The world's first public ledger of every single compromised one-time password. Embrace the inevitable.**

---

## Live Demo

See your 'secrets' exposed: **https://everyotp.bugbountyhunting.com**
![image](https://github.com/user-attachments/assets/f987a607-e6f1-4567-9d2d-7e13fb473b5d)

---

## Concept

In a world plagued by endless data breaches and security fatigue, EveryOTP cuts through the noise. Why wait for your one-time password to be compromised when you can confirm its inescapable fate right now? This project is a satirical commentary on the futility of traditional digital security in the face of omnipresent threats and the sheer scale of modern credential compromises.

We've indexed *every single possible* 4, 5, 6, 7, and 8-digit numerical One-Time Password. That's over **111,111,000 unique 'secrets'** – all publicly available, all pre-compromised. Your current OTP? It's here. Your next one? It's here too.

### Key Features

*   **Universal Breach Ledger:** A high-performance, virtualized list of every possible OTP, ordered "randomly" (using a deterministic bijective map) for endless scrolling.
*   **Automatic Scope Detection:** Type your OTP; the system automatically detects its digit length (4-8 digits) and adjusts the ledger scope.
*   **Instant Locate & Highlight:** Find any specific OTP's exact position in the ledger in milliseconds.
*   **"Tweet Secret" Button:** Share your existential discovery with the world directly from the ledger.
*   **Magic Scroll:** Experience the relentless march of compromised data with an idle auto-scroll that pauses on user interaction.
*   **Client-Side Operation:** All computations and searches happen directly in your browser. Your input is never sent to any server. No data is collected or stored.

## Inspiration & Attribution

This project is built with dark humor and profound respect for the pioneering work in digital futility:

*   **@IceSolst** (Solstice) for the viral "Every Password" concept.
*   **@itseieio** (Nolen Royalty) for the technical brilliance behind `everyuuid.com` and its groundbreaking virtual scrolling, deterministic ordering, and real-time search over unimaginably large number spaces. His blog post ["Writing down every UUID"](https://eieio.games/blog/writing-down-every-uuid) was a primary technical inspiration.

Built by **[@payloadartist](https://twitter.com/payloadartist)**.

## How it Works (The Magic Behind the Nihilism)

This application is a single HTML file running entirely in your browser. There's no backend server involved for the OTP lookup.

1.  **Virtual Scrolling:** Instead of rendering all 111+ million OTPs, only the visible ones (and a small buffer) are drawn. Your "scroll position" is stored as a `BigInt`.
2.  **Deterministic Ordering:** Each linear integer index (e.g., 0, 1, 2, ...) is mapped to a unique, "random-looking" OTP string using a **bijective function** based on modular arithmetic (specifically, multiplication by a coprime number and its modular inverse). This ensures every OTP appears exactly once, and its linear index can always be recovered.
3.  **Instant Search:** When you type an OTP, the bijective function is reversed to calculate its exact linear index. The view then animates smoothly to that position.
4.  **No Data Sent:** Because the mapping is deterministic and calculated locally, your search queries and the OTPs you view are never transmitted anywhere.

## Development & Contribution

This is a client-side project contained entirely within `index.html`. To run it locally, simply open `index.html` in your web browser.

Pull requests for enhancements or additional satirical features are welcome!

## License

This project is open-source under the MIT License. See the `LICENSE` file for details.
