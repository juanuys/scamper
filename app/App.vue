// App.vue

<template lang="pug">
    .container
        h1 Random SCAMPER

        div(v-if="prompt=='substitute'")
            h1 Substitute
            p Overall, the question to think about here is this: What can I substitute or change in my product, problem or process? You should think about substituting part(s) of your product or process for something else.
            p.guide Guiding question: {{question}}
            button(v-on:click='showAll = !showAll') Show/Hide all questions for this prompt
            ul.all(v-if="showAll")
                li(v-for="q in questions") {{q}}


        div(v-if="prompt=='combine'") 
            h1 Combine
            p The overall question to think about here is: How can I combine two or more parts of my product, problem, or process so as to achieve a different product, problem, or process to enhance synergy? Creative thinking involves combining previously unrelated ideas, products, or services in order to create something new and innovative.
            p.guide Guiding question: {{question}}
            button(v-on:click='showAll = !showAll') Show/Hide all questions for this prompt
            ul.all(v-if="showAll")
                li(v-for="q in questions") {{q}}

        div(v-if="prompt=='adapt'") 
            h1 Adapt
            p Overall, the question you need to think about is: What can I adapt in my product, problem, or process? Think about which parts of the product or process you could adapt so as to solve your problem.
            p.guide Guiding question: {{question}}
            button(v-on:click='showAll = !showAll') Show/Hide all questions for this prompt
            ul.all(v-if="showAll")
                li(v-for="q in questions") {{q}}

        div(v-if="prompt=='modify'") 
            h1 Modify #[span (Also Magnify and Minify)]
            p Overall, the question you need to focus on is this: What can I modify or put more or less #[a(href='https://www.interaction-design.org/literature/topics/emphasis') emphasis] on in my product, problem, or process? Can I change the item in some way? Can I change meaning, colour, motion, sound, smell, form, or shape? It’s time to magnify or exaggerate your idea, product, problem, or process—or to minify it. These questions will give you new insights about which components are the most important ones. Think about changing part or all of the current situation or product. Alternatively, distort the product in an unusual way.
            p.guide Guiding question: {{question}}
            button(v-on:click='showAll = !showAll') Show/Hide all questions for this prompt
            ul.all(v-if="showAll")
                li(v-for="q in questions") {{q}}

        div(v-if="prompt=='put'") 
            h1 Put to Another Use
            p The overall question to consider here is this: How can I put the thing to other uses? What are new ways to use the product or service? Can I reach out to other users if I modify the product? Is there another market for the product? It’s time to work out how you may be able to put your current product or idea to other uses and purposes.
            p.guide Guiding question: {{question}}
            button(v-on:click='showAll = !showAll') Show/Hide all questions for this prompt
            ul.all(v-if="showAll")
                li(v-for="q in questions") {{q}}

        div(v-if="prompt=='eliminate'") 
            h1 Eliminate
            p Your overall question to consider here is: What can I eliminate or simplify in my product, design, or service? Think of what might happen if you were to eliminate, simplify, reduce, or minimise parts of your idea. If you continue to trim your idea, service, or process—you can gradually narrow your challenge down to that part or function that is most important.
            p.guide Guiding question: {{question}}
            button(v-on:click='showAll = !showAll') Show/Hide all questions for this prompt
            ul.all(v-if="showAll")
                li(v-for="q in questions") {{q}}

        div(v-if="prompt=='reverse'") 
            h1 Rearrange #[span Or Reverse]
            p Overall, you have to ask yourself this question: How can I change, reorder, or reverse the product or problem? What would I do if I had to do this process in reverse?
            p.guide Guiding question: {{question}}
            button(v-on:click='showAll = !showAll') Show/Hide all questions for this prompt
            ul.all(v-if="showAll")
                li(v-for="q in questions") {{q}}

        p.spacer
        p Boost your creativity with the randomised SCAMPER technique. Inspired by my very own box of SCAMPER cards: #[a(href='https://www.penguinrandomhouse.com/books/198258/thinkpak-by-michael-michalko/') Creative Thinkpak]
        p.smaller How is this similar to Thinkpak? It uses the Thinkpak "Random Strategy" where you draw a card (one of the SCAMPERs) at random, then try to apply the questions to your problem. I think looking at a random prompt instead of going through the entire SCAMPER list constrains you, which can be a good prompt for thinking outside the box. If it's not applicable, randomise again. Rinse, repeat until you're satisfied with the ideas you've come up with. (What this misses are the "Evaluate" cards, but at this point I suggest you purchase your own *pak* 😀 )

        span.action Refresh the page for another random SCAMPER.
        p Copyright #[a(href='https://www.interaction-design.org/literature/article/learn-how-to-use-the-best-ideation-methods-scamper') Interaction Design Foundation, Learn How to Use the Best Ideation Methods: SCAMPER]
        p See also #[a(href='https://www.mindtools.com/pages/article/newCT_02.htm') MindTools SCAMPER]

        p #[a(href='https://github.com/juanuys/scamper') Made] by #[a(href='https://juanuys.com') Juan Uys]
</template>

<script lang="ts">
import Vue from "vue"

const prompts = ["substitute", "combine", "adapt", "modify", "put", "eliminate", "reverse"]
const questions = {
    "substitute": [
        "What can I substitute so as to make an improvement?",
        "How can I substitute the place, time, materials or people?",
        "Can I substitute one part for another or change any parts?",
        "Can I replace someone involved?",
        "Can I change the rules?",
        "Should I change the name?",
        "Can I use other ingredients or materials?",
        "Can I use other processes or procedures?",
        "Can I change its shape, colour, roughness, sound or smell?",
        "Can I use this idea for other projects?",
        "Can I change my feelings or attitude towards it?",
    ],
    "combine": [
        "What ideas, materials, features, processes, people, products, or components can I combine?",
        "Can I combine or merge this or that with other objects?",
        "What can I combine so as to maximize the number of uses?",
        "What can I combine in order to lower the costs of production?",
        "Which materials could I combine?",
        "Where can I build synergy?",
        "Which are the best elements I can bring together so as to achieve a particular result?",
    ],
    "adapt": [
        "Which part of the product could I change?",
        "Could I change the characteristics of a component?",
        "Can I seek inspiration in other products or processes, but in a different context?",
        "Does the history offer any solutions?",
        "Which ideas could I adapt, copy, or borrow from other people’s products?",
        "What processes should I adapt?",
        "Can I adapt the context or target group?",
        "What can I adapt in this or that way in order to make this result?",
    ],
    "modify": [
        "What can I magnify or make larger?",
        "What can I tone down or delete?",
        "Could I exaggerate or overstate buttons, colours, size…?",
        "Could I grow the target group?",
        "What can be made higher, bigger, or stronger?",
        "Can I increase its speed or frequency?",
        "Can I add extra features?",
        "How can I add extra value?",
        "What can you remove or make smaller, condensed, lower, shorter or lighter—or streamline, split up or understate?",
        "What can I change in this way or that way so as to achieve such and such a result?",
    ],
    "put": [
        "What else can it be used for?",
        "How would a child use it?—an older person?",
        "How would people with different disabilities use it?",
        "Which other target group could benefit from this product?",
        "What other kind of user would need or want my product?",
        "Who or what else may be able to use it?",
        "Can it be used by people other than those it was originally intended for?",
        "Are there new ways to use it in its current shape or form?",
        "Would there be other possible uses if I were to modify the product?",
        "How can I reuse something in a certain way by doing what to it?",
    ],
    "eliminate": [
        "What can I remove without altering its function?",
        "Can I reduce time or components?",
        "What would happen if I removed a component or part of it?",
        "Can I reduce effort?",
        "Can I cut costs?",
        "How can I simplify it?",
        "What’s non-essential or unnecessary?",
        "Can I eliminate the rules?",
        "Can I make it smaller?",
        "Can I split my product into different parts?",
        "I can eliminate what by doing what?",
    ],
    "reverse": [
        "What can I rearrange in some way – can I interchange components, the pattern, or the layout?",
        "Can I change the pace or schedule?",
        "What would I do if part of your problem, product or process worked in reverse?",
        "I can rearrange what in what way such that this happens?",
    ]
}

export default Vue.extend({
    data() {
        return {
            showAll: false
        }
    },
    computed: {
        prompt: function () {
            return prompts[Math.floor(Math.random() * prompts.length)]
            // return "substitute"
        },
        questions: function () {
            return questions[this.prompt]
        },
        question: function () {
            return this.questions[Math.floor(Math.random() * this.questions.length)]
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
.container > div {
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
p.spacer {
    padding-top: 50px;
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
</style>
