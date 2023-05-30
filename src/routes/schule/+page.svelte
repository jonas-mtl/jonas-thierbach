<script lang="ts">
    import '$lib/styles/schule/index.scss'
    import '$lib/styles/blog.scss'

    let whileLoop = {
        console: "",
        store: [false, false, false, false, false],
        current: 0,
        script: [0, 2, 3, 4, 2, 3, 4, 2, 3, 4, 2, 3, 4, 2, 3, 4, 2, 3, 4, 2, 3, 4, 2, 3, 4, 2, 3, 4]
    }

    const whileLoopAction = () => {
        const activeSlot = whileLoop.script[whileLoop.current]
        if(activeSlot == undefined && whileLoop.current != 0) return;

        whileLoop.store = [activeSlot == 0 ? true : false, activeSlot == 1 ? true : false, activeSlot == 2 ? true : false, activeSlot == 3 ? true : false, activeSlot == 4 ? true : false]

        if(activeSlot == 3) whileLoop.console = whileLoop.console + "<p>> Das ist ein Test!</p>"

        whileLoop.current++;
    }

    let doWhileLoop = {
        console: "",
        store: [false, false, false, false, false, false, false, false],
        i: 1,
        current: 0,
        script: [0, 2, 3, 4, 5, 2, 3, 4, 5, 2, 3, 4, 5, 7]
    }

    const doWhileLoopAction = () => {
        const activeSlot = doWhileLoop.script[doWhileLoop.current]
        if(activeSlot == undefined && doWhileLoop.current != 0) return;

        doWhileLoop.store = [activeSlot == 0 ? true : false, activeSlot == 1 ? true : false, activeSlot == 2 ? true : false, activeSlot == 3 ? true : false, activeSlot == 4 ? true : false, activeSlot == 5 ? true : false, activeSlot == 6 ? true : false, activeSlot == 7 ? true : false]

        if(activeSlot == 3) {
            doWhileLoop.console = doWhileLoop.console + `<p>> ${doWhileLoop.i}</p>`
            doWhileLoop.i++;
        } 

        if(activeSlot == 7) {
            doWhileLoop.console = doWhileLoop.console + `<p>> Fertig!</p>`
        } 

        doWhileLoop.current++;
    }

    let forLoop = {
        console: "",
        store: [false, false, false, false, false, false, false, false],
        i: 1,
        current: 0,
        script: [0, 1, 2, 0, 1, 2, 0, 1, 2, 4]
    }

    const forLoopAction = () => {
        const activeSlot = forLoop.script[forLoop.current]
        if(activeSlot == undefined && forLoop.current != 0) return;

        forLoop.store = [activeSlot == 0 ? true : false, activeSlot == 1 ? true : false, activeSlot == 2 ? true : false, activeSlot == 3 ? true : false, activeSlot == 4 ? true : false, activeSlot == 5 ? true : false, activeSlot == 6 ? true : false, activeSlot == 7 ? true : false]

        if(activeSlot == 1) {
            forLoop.console = forLoop.console + `<p>> ${forLoop.i}</p>`
            forLoop.i++;
        } 

        if(activeSlot == 4) {
            forLoop.console = forLoop.console + `<p>> Fertig!</p>`
        } 

        forLoop.current++;
    }
</script>

<main>
    <div class="content">
        <h2>Java Loops</h2>

        <div class="information">
            <p>by Jonas</p>
            <p>Posted May 30, 2023</p>
        </div>

        <h3>1. while Loop</h3>
        <p>Die while-Schleife durchläuft einen Codeblock so lange, wie eine bestimmte Bedingung erfüllt ist:</p>

        <div class="java">
            <div class="code-header">
                <span>Java</span>
                <button on:click={whileLoopAction}>Start</button>
            </div>
            <div class="code">
                <code>
                    <pre class={whileLoop.store[0] ? "highlight" : ""}>int test = 1;</pre>
                    <pre class={whileLoop.store[1] ? "highlight" : ""}> </pre>
                    <pre class={whileLoop.store[2] ? "highlight" : ""}>while (test == 1) {'{'}</pre>
                    <pre class={whileLoop.store[3] ? "highlight" : ""}>   System.out.println("Das ist ein Test!");</pre>
                    <pre class={whileLoop.store[4] ? "highlight" : ""}>{'}'}</pre>
                </code>
            </div>
        </div>

        <div class="console">
            <p class="title">Output:</p>
            {@html whileLoop.console}
        </div>

        <h3>2. do-while Loop</h3>
        <p>Der Codeblock wird zuerst einmal ausgeführt und anschließend wird überprüft, ob die Bedingung erfüllt ist:</p>

        <div class="java">
            <div class="code-header">
                <span>Java</span>
                <button on:click={doWhileLoopAction}>Start</button>
            </div>
            <div class="code">
                <code>
                    <pre class={doWhileLoop.store[0] ? "highlight" : ""}>int test = 1;</pre>
                    <pre class={doWhileLoop.store[1] ? "highlight" : ""}> </pre>
                    <pre class={doWhileLoop.store[2] ? "highlight" : ""}>do {'{'}</pre>
                    <pre class={doWhileLoop.store[3] ? "highlight" : ""}>   System.out.println(test);</pre>
                    <pre class={doWhileLoop.store[4] ? "highlight" : ""}>   test++;</pre>
                    <pre class={doWhileLoop.store[5] ? "highlight" : ""}>{'}'} while (test {'<'} 4) </pre>
                    <pre class={doWhileLoop.store[6] ? "highlight" : ""}> </pre>
                    <pre class={doWhileLoop.store[7] ? "highlight" : ""}>System.out.println("Fertig!");</pre>
                </code>
            </div>
        </div>

        <div class="console">
            <p class="title">Output:</p>
            {@html doWhileLoop.console}
        </div>

        <h3>3. for Loop</h3>
        <p>Falls man genau weiß, wie oft ein Codeblock wiederholt werden soll, verwendet man die for-Schleife:</p>

        <div class="java">
            <div class="code-header">
                <span>Java</span>
                <button on:click={forLoopAction}>Start</button>
            </div>
            <div class="code">
                <code>
                    <pre class={forLoop.store[0] ? "highlight" : ""}>for (int test = 1; test {'<'} 4; test++) {'{'}</pre>
                    <pre class={forLoop.store[1] ? "highlight" : ""}>   System.out.println(test);</pre>
                    <pre class={forLoop.store[2] ? "highlight" : ""}>{'}'}</pre>
                    <pre class={forLoop.store[3] ? "highlight" : ""}> </pre>
                    <pre class={forLoop.store[4] ? "highlight" : ""}>System.out.println("Fertig!");</pre>
                </code>
            </div>
        </div>

        <div class="console">
            <p class="title">Output:</p>
            {@html forLoop.console}
        </div>
    </div>


    <div class="navigator">
        <h3>Inhalt</h3>
        <ul>
            <li>While Loop</li>
            <li>Do-While Loop</li>
            <li>For Loop</li>
        </ul>
    </div>
</main>