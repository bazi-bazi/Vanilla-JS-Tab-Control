# Vanilla-JS-Tab-Control
Website tab control, created using pure JS


// We are saerching for specific tabs and tab contents using querySelectorAll and querySelector

    let tab = document.querySelectorAll('.info-header-tab'),
        info = document.querySelector('.info-header'),
        tabContent = document.querySelectorAll('.info-tabcontent');


    // We are creating a function for Hide tab content - We need to show just one tab in a front page  
    // (არგუმენტი a გვჭირდება ნუმერაციისთვის, რომ თაბი და თაბ კონტენტი დაემთხვეს ერთმანეთს ) 
    function hideTabContent(a) {
        for (let i = a; i < tabContent.length; i++) {
            tabContent[i].classList.remove('show');
            tabContent[i].classList.add('hide');
        }
    }

    hideTabContent(1);

    // At a same way we are creating function to show selected tab and hide unselected (vise versa)
    //(არგუმენტი b გვჭირდება ნუმერაციისთვის, რომ თაბი და თაბ კონტენტი დაემთხვეს ერთმანეთს) 

    function showTabContent(b) {
        if (tabContent[b].classList.contains('hide')) {
            tabContent[b].classList.remove('hide');
            tabContent[b].classList.add('show');
        }
    }

    // Add event listener to tab menu to check which tab is clicked

    info.addEventListener('click', function (event) {
        let target = event.target;

        if (target && target.classList.contains('info-header-tab')) {
            for (let i = 0; i < tab.length; i++) {
                if (target == tab[i]) {
                    hideTabContent(0);
                    showTabContent(i);
                    break;
                }
            }

        }


    });
