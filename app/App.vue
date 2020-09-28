// App.vue

<template lang="pug">
    .container
        h1 Random SCAMPER

        div.scamper
            h1 {{title}} #[span(v-if="altTitle") {{altTitle}} ]
            p(v-html="intro")
            p.guide Guiding question: {{question}}
            button(v-on:click='showAll = !showAll') Show/Hide all questions for this prompt
            ul.all(v-if="showAll")
                li(v-for="q in questions") {{q}}

        span.action Refresh the page for another random SCAMPER.

        div.colophon
            h1(v-on:click='showColophon = !showColophon') Colophon
            div(v-if="showColophon")
                p Boost your creativity with the randomised SCAMPER technique. Inspired by my very own box of SCAMPER cards: #[a(href='https://www.penguinrandomhouse.com/books/198258/thinkpak-by-michael-michalko/') Creative Thinkpak]
                p.smaller How is this similar to Thinkpak? It uses the Thinkpak "Random Strategy" where you draw a card (one of the SCAMPERs) at random, then try to apply the questions to your problem. I think looking at a random prompt instead of going through the entire SCAMPER list constrains you, which can be a good prompt for thinking outside the box. If it's not applicable, randomise again. Rinse, repeat until you're satisfied with the ideas you've come up with. (What this misses are the "Evaluate" cards, but at this point I suggest you purchase your own *pak* 😀 )
        
                p Copyright #[a(href='https://www.interaction-design.org/literature/article/learn-how-to-use-the-best-ideation-methods-scamper') Interaction Design Foundation, Learn How to Use the Best Ideation Methods: SCAMPER]
                p See also #[a(href='https://www.mindtools.com/pages/article/newCT_02.htm') MindTools SCAMPER]

                p #[a(href='https://github.com/juanuys/scamper') Made] by #[a(href='https://juanuys.com') Juan Uys]
</template>

<script lang="ts">
import Vue from "vue"
import data from "./data.json"
import pug from "pug"

export default Vue.extend({
    data() {
        return {
            showAll: false,
            showColophon: false
        }
    },
    computed: {
        prompts: function () {
            return Object.keys(data)
        },
        prompt: function () {
            return this.prompts[Math.floor(Math.random() * this.prompts.length)]
            // return "modify"
        },
        questions: function () {
            return data[this.prompt].questions
        },
        question: function () {
            return this.questions[Math.floor(Math.random() * this.questions.length)]
        },
        title: function () {
            return data[this.prompt].title
        },
        intro: function () {
            return data[this.prompt].intro
        },
        altTitle: function () {
            return data[this.prompt].alt
        }
    }
})
</script>

<style lang="scss" scoped>
.container {
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    font-size: 1.2em;
    color: #333;
}
.container > * {
    margin: 20px;
}
h1 > span {
    font-size: 0.5em;
    color: #777;
}
div.scamper {
    background-color: lightblue;
    padding: 15px;
}
.container > h1 {
    font-size: 1.3em;
}
.action {
    background-color: lightcoral;
    color: rebeccapurple;
    padding: 8px;
}
p.smaller {
    font-size: smaller;
}
p.guide {
    background-color: lightyellow;
    color: darkolivegreen;
    padding: 8px;
}
ul.all {
    font-size: smaller;
}
button {
    border: 0;
    background: none;
    box-shadow: none;
    border-radius: 0px;
    background-color: lightgrey;
    padding: 8px;
}
button::after {
    content: ' >>'
}
div.colophon h1 {
    cursor: pointer;
    font-size: smaller;
    color: darkgray;
}
div.colophon {
    position: absolute;
    bottom: 50px;
}
</style>
