// ==========================================
// TASIN.DEV - MAIN JAVASCRIPT
// ==========================================


// ==========================================
// 1. MOBILE MENU
// ==========================================

const mobileMenu = document.querySelector('#mobile-menu');
const navLinks = document.querySelector('.nav-links');

if (mobileMenu && navLinks) {

    mobileMenu.addEventListener('click', () => {

        mobileMenu.classList.toggle('active');
        navLinks.classList.toggle('active');

    });


    // Close menu when a link is clicked

    document.querySelectorAll('.nav-links a').forEach(link => {

        link.addEventListener('click', () => {

            mobileMenu.classList.remove('active');
            navLinks.classList.remove('active');

        });

    });

}


// ==========================================
// 2. ACTIVE NAVIGATION SECTION
// ==========================================

const sections = document.querySelectorAll('section');
const navItems = document.querySelectorAll('.nav-links a');

function updateActiveSection() {

    let currentSectionId = '';

    sections.forEach(section => {

        const sectionTop = section.offsetTop;
        const sectionHeight = section.offsetHeight;

        if (
            window.scrollY >=
            sectionTop - sectionHeight / 3
        ) {

            currentSectionId = section.getAttribute('id');

        }

    });


    navItems.forEach(item => {

        item.classList.remove('active');

        const href = item.getAttribute('href');

        if (
            href &&
            href === `#${currentSectionId}`
        ) {

            item.classList.add('active');

        }

    });

}

window.addEventListener('scroll', updateActiveSection);


// ==========================================
// 3. LIVE TYPING HEADLINE
// ==========================================

document.addEventListener('DOMContentLoaded', () => {

    const typingText =
        document.getElementById('typing-text');


    // If the HTML element doesn't exist,
    // stop the animation.

    if (!typingText) {

        console.error(
            'ERROR: #typing-text was not found in HTML.'
        );

        return;

    }


    const words = [

        'CSE Student',

        'Aspiring AI Engineer',

        'Web Developer',

        'Problem Solver',

        'Tech Enthusiast',

        'Future Software Engineer'

    ];


    let wordIndex = 0;

    let charIndex = 0;

    let isDeleting = false;


    function typeEffect() {

        const currentWord =
            words[wordIndex];


        // ==================================
        // TYPING
        // ==================================

        if (!isDeleting) {

            typingText.textContent =
                currentWord.substring(
                    0,
                    charIndex + 1
                );

            charIndex++;


            // Word finished

            if (
                charIndex ===
                currentWord.length
            ) {

                isDeleting = true;

                setTimeout(
                    typeEffect,
                    1800
                );

                return;

            }


            setTimeout(
                typeEffect,
                80
            );

        }


        // ==================================
        // DELETING
        // ==================================

        else {

            typingText.textContent =
                currentWord.substring(
                    0,
                    charIndex - 1
                );

            charIndex--;


            // Word completely deleted

            if (charIndex === 0) {

                isDeleting = false;

                wordIndex++;


                // Start again from first word

                if (
                    wordIndex >=
                    words.length
                ) {

                    wordIndex = 0;

                }


                setTimeout(
                    typeEffect,
                    400
                );

                return;

            }


            setTimeout(
                typeEffect,
                45
            );

        }

    }


    // Start animation

    typeEffect();

});
