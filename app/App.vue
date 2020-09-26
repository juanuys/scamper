// App.vue

<template lang="pug">
    .container
        h1 Random SCAMPER

        div(v-if="question=='substitute'")
            h1 Substitute
            p Overall, the question to think about here is this: What can I substitute or change in my product, problem or process? You should think about substituting part(s) of your product or process for something else.
            p Guiding questions:
            ul
                li What can I substitute so as to make an improvement?
                li How can I substitute the place, time, materials or people?
                li Can I substitute one part for another or change any parts?
                li Can I replace someone involved?
                li Can I change the rules?
                li Should I change the name?
                li Can I use other ingredients or materials?
                li Can I use other processes or procedures?
                li Can I change its shape, colour, roughness, sound or smell?
                li Can I use this idea for other projects?
                li Can I change my feelings or attitude towards it?

        div(v-if="question=='combine'") 
            h1 Combine
            p The overall question to think about here is: How can I combine two or more parts of my product, problem, or process so as to achieve a different product, problem, or process to enhance synergy? Creative thinking involves combining previously unrelated ideas, products, or services in order to create something new and innovative.
            p Guiding questions:
            ul
                li What ideas, materials, features, processes, people, products, or components can I combine?
                li Can I combine or merge this or that with other objects?
                li What can I combine so as to maximize the number of uses?
                li What can I combine in order to lower the costs of production?
                li Which materials could I combine?
                li Where can I build synergy?
                li Which are the best elements I can bring together so as to achieve a particular result?

        div(v-if="question=='adapt'") 
            h1 Adapt
            p Overall, the question you need to think about is: What can I adapt in my product, problem, or process? Think about which parts of the product or process you could adapt so as to solve your problem.
            p Guiding questions:
            ul
                li Which part of the product could I change?
                li Could I change the characteristics of a component?
                li Can I seek inspiration in other products or processes, but in a different context?
                li Does the history offer any solutions?
                li Which ideas could I adapt, copy, or borrow from other people’s products?
                li What processes should I adapt?
                li Can I adapt the context or target group?
                li What can I adapt in this or that way in order to make this result?

        div(v-if="question=='modify'") 
            h1 Modify #[span (Also Magnify and Minify)]
            p Overall, the question you need to focus on is this: What can I modify or put more or less #[a(href='https://www.interaction-design.org/literature/topics/emphasis') emphasis] on in my product, problem, or process? Can I change the item in some way? Can I change meaning, colour, motion, sound, smell, form, or shape? It’s time to magnify or exaggerate your idea, product, problem, or process—or to minify it. These questions will give you new insights about which components are the most important ones. Think about changing part or all of the current situation or product. Alternatively, distort the product in an unusual way.
            p Guiding questions:
            ul
                li What can I magnify or make larger?
                li What can I tone down or delete?
                li Could I exaggerate or overstate buttons, colours, size…?
                li Could I grow the target group?
                li What can be made higher, bigger, or stronger?
                li Can I increase its speed or frequency?
                li Can I add extra features?
                li How can I add extra value?
                li What can you remove or make smaller, condensed, lower, shorter or lighter—or streamline, split up or understate?
                li What can I change in this way or that way so as to achieve such and such a result?

        div(v-if="question=='put'") 
            h1 Put to Another Use
            p The overall question to consider here is this: How can I put the thing to other uses? What are new ways to use the product or service? Can I reach out to other users if I modify the product? Is there another market for the product? It’s time to work out how you may be able to put your current product or idea to other uses and purposes.
            p Guiding questions:
            ul
                li What else can it be used for?
                li How would a child use it?—an older person?
                li How would people with different disabilities use it?
                li Which other target group could benefit from this product?
                li What other kind of user would need or want my product?
                li Who or what else may be able to use it?
                li Can it be used by people other than those it was originally intended for?
                li Are there new ways to use it in its current shape or form?
                li Would there be other possible uses if I were to modify the product?
                li How can I reuse something in a certain way by doing what to it?

        div(v-if="question=='eliminate'") 
            h1 Eliminate
            p Your overall question to consider here is: What can I eliminate or simplify in my product, design, or service? Think of what might happen if you were to eliminate, simplify, reduce, or minimise parts of your idea. If you continue to trim your idea, service, or process—you can gradually narrow your challenge down to that part or function that is most important.
            p Guiding questions:
            ul
                li What can I remove without altering its function?
                li Can I reduce time or components?
                li What would happen if I removed a component or part of it?
                li Can I reduce effort?
                li Can I cut costs?
                li How can I simplify it?
                li What’s non-essential or unnecessary?
                li Can I eliminate the rules?
                li Can I make it smaller?
                li Can I split my product into different parts?
                li I can eliminate what by doing what?

        div(v-if="question=='reverse'") 
            h1 Rearrange #[span Or Reverse]
            p Overall, you have to ask yourself this question: How can I change, reorder, or reverse the product or problem? What would I do if I had to do this process in reverse?
            p Guiding questions:
            ul
                li What can I rearrange in some way – can I interchange components, the pattern, or the layout?
                li Can I change the pace or schedule?
                li What would I do if part of your problem, product or process worked in reverse?
                li I can rearrange what in what way such that this happens?

        p Boost your creativity with the randomised SCAMPER technique. Inspired by my very own box of SCAMPER cards: #[a(href='https://www.penguinrandomhouse.com/books/198258/thinkpak-by-michael-michalko/') Creative Thinkpak]
        p How is this different? When you're stuck, instead of asking ALL 7 questions, just ask one random question. This constrains you, which can be a good prompt for thinking outside the box.

        span.action Refresh the page for another random SCAMPER.
        p Copyright #[a(href='https://www.interaction-design.org/literature/article/learn-how-to-use-the-best-ideation-methods-scamper') Interaction Design Foundation, Learn How to Use the Best Ideation Methods: SCAMPER]
        p See also #[a(href='https://www.mindtools.com/pages/article/newCT_02.htm') MindTools SCAMPER]

        p Made by #[a(href='https://juanuys.com') Juan Uys]
</template>

<script lang="ts">
import Vue from "vue"

const questions = ["substitute", "combine", "adapt", "modify", "put", "eliminate", "reverse"]

export default Vue.extend({
    data() {
        return {
            question: questions[Math.floor(Math.random() * questions.length)]
        }
    }
})
</script>

<style lang="scss" scoped>
.container {
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    font-size: 1.2em;
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
</style>