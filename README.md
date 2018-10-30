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
