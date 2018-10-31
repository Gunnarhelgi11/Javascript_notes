# Javascript_notes
function checkUsername() {                                              // Búum til fallið
    let elMsg = document.getElementById('feedback');                    // Náum í elementið í HTMl skjalinu sem er með id "feedback"
    if (this.value.length < 5) {                                        // Athugar hvort það sem kallar á fallið sé styttra en 5 á lengd
        elMsg.textContent = 'Username must be 5 characters or more';    // Setjið skilaboð í "feedback"
    } else {                                                            // Ef lengra en 5 þá keyrist þessi kóði
        elMsg.textContent = '';                                         // Tæmir það sem stendur í "feedback"
    }
}


let elUsername = document.getElementById('username');                   // Náum í það sem er með id "username"
elUsername.onblur = checkUsername;                                      // Þegar fókusinn fer af elementinu "username" þá virkjast fallið





//Önnur aðferð til að gera það sama
let elUsername = document.getElementById('username');
let elMsg      = document.getElementById('feedback');

function checkUsername(minLength) {
    if (elUsername.value.length < minLength) {

        elMsg.innerHTML = 'Username must be ' + minLength + ' characters or more';
    } else {
        elMsg.innerHTML = '';
    }
}

elUsername.addEventListener('blur', function () {
    checkUsername(5);
}, false);

//----------------------------------------


function getTarget(e) {
    // Búum til fallið og látum það taka inntak (input) með sér
    return e.target || e.srcElement;
    // Náum í það element sem virkaði viðburð (event)
}

function itemDone(e) {
    //Búum til fallið og látum það taka inntak (input) með sér
    let target, elParent, elGrandparent;
    // skilgreinum breytur
    target = getTarget(e);
    // náum í elementið sem var smellt á og setjum í breytuna target
}



if (target.nodeName.toLowerCase() == "a") {
    elListItem = target.parentNode;
    elList = elListItem.parentNode;
    elList.removeChild(elListItem);
}
if (target.nodeName.toLowerCase() == "em") {
    elListItem = target.parentNode.parentNode;
    elList = elListItem.parentNode;
    elList.removeChild(elListItem);
}


e.preventDefault();

// setjum upp viðburðarhlustun (event listeners) sem kalla á itemDone() þegar smellt er á elementin
let el = document.getElementById('shoppinglist');   // Náum í shoppinglist elementið
el.addEventListener('click', function (e) {         // Bætum við viðburði á click
    itemDone(e);                                    // Viðburðurinn kallar á fallið itemDone með e sem inntak
}, false);






//ef þið viljið gefa ákveðnu element fókus þegar vefsíðan er keyrð upp
function setup(){                                       //búið til fallið setup
    let textInput;                                      //skilgreinið breytuna
    textInput = document.getElementById('username');    //náið í elementið username
    textInput.focus();                                  // elementinu username gefið
}
window.addEventListener('load', setup, false);          // Þegar síðan er hlaðin upp







//Kallar á ábendingu þegar verið er að skrifa en viðvörun ef farið er ú
        function checkUsername() {                              // Búið til fallið
            let username = el.value;                            // setjuð gildið inní breytunni el inní username
            if (username.length < 5) {                          // Ef username < 5 stafir
                elMsg.className = 'warning';                    // Breytið þá um class á elMsg yfir í warning
                elMsg.textContent = 'Not long enough yet...';   // Uppfærið skilaboðin í elMsg
            }else {                                             // annars
                elMsg.textContent = '';                         // Tæmið skilaboðin
            }
        }

        function tipUsername() {                                        // Búið til fallið
            elMsg.className = 'tip';                                    // Breytið um nafn á class
            elMsg.innerHTML = 'Username must be at least 5 characters'; // Uppfærið skilaboðin í elMsg
        }

        let el = document.getElementById('username');       // Náið í elementið username
        let elMsg = document.getElementById('feedback');    // Náið í elementið feedback

// hvort að elementið username fær fókus eða missir, kallið á viðeigandi breytur
        el.addEventListener('focus', tipUsername, false);
        el.addEventListener('blur', checkUsername, false);





// Búið til HTML kóðann fyrir skilaboðin
    let msg = '<div class =\"header"\><a id=\"close\" href=\"#\">close X</a></div>';
    msg += '<div><h2>System Maintenance</h2>';
    msg += 'Our servers are being updated between 3 and 4 a.m. ';
    msg += 'During this time, there may be minor disruptions to service.</div>';

    let elNote = document.createElement('div');
    elNote.setAttribute('id', 'note');
    elNote.innerHTML = msg;
    document.body.appendChild(elNote);

    function dismissNote() {
        document.body.removeChild(elNote);
    }

    let elClose = document.getElementById('close');
    elClose.addEventListener('clock', dismissNote, false);// þegar smellt er á elementið
    // close að þá er kallað á fallið dismissNote

    // Hvernig greinum við hvaða lykil á lyklaborðinu var smellt á
    let message;

    function charCount(e) {
        let textEntered, charDisplay, counter, lastkey;
        textEntered = document.getElementById('message').value;
        charDisplay = document.getElementById('charactersLeft')
        counter = (180 - (textEntered.length));
        charDisplay.textContent = 'Last key in ASCII code: ' + e.keyCode;
    }
    message = document.getElementById('message');
    message.addEventListener('keyup', charCount, false);





