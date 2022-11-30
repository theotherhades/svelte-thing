<script>
    let money = 0;
    let multiplier = 1;
    let factories = 0;

    function updateMoney() {
        money += multiplier;
    }

    function increaseMultiplier() {
        if (money >= 50) {
            multiplier += 1;
            money -= 50;
        } else {
            alert("You don't have enough money!");
        }
    }

    function addFactory() {
        if (money >= 30) {
            setInterval(() => {money += 1}, 1000);
            money -= 30;
            factories += 1;
        } else {
            alert("You don't have enough money!");
        }
    }
</script>

<center>
    <h1>money game in svelte</h1>
    <button on:click={updateMoney}>
        Get money<br>${money}
    </button>
    <br>
    Multiplier: ${multiplier}/click | Factory earnings: ${factories}/sec
    <br><br>

    <h3>--- SHOP ---</h3>
    <button on:click={increaseMultiplier}>
        Multiplier +1<br>[+${multiplier}/click -> +${multiplier + 1}/click]
        <br><br>
        $50
    </button>
    <button on:click={addFactory}>
        Buy Factory<br>[+$1/sec]
        <br><br>
        $30
    </button>
</center>