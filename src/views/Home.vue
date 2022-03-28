<template>
  <div class="justify-center max-w-md mt-10">
    <h1 class="font-extrabold tracking-tigh text-3xl leading-10">
      Ready for the challenge?
    </h1>
    <div class="mt-8">
      <section>
        <h2 class="font-bold text-2xl leading-6">Exercise 1</h2>
        <div class="mt-5">
          <p>
            In the first exercise the goal would be to extend the current app
            with some additional output. For this you should integrate an public
            available Rest-API or GraphQL-API (see below for examples).
          </p>
          <p>
            It's your own decision what kind of output you use and in which way
            it will be displayed, but it should be in a creative way and you can
            use this possibility to show us your existing skills. For example
            you can add a list output as a starting point and show additional
            information in a detail page (or other output types).
          </p>
          <br />
          <p>Here are some examples for a public available API:</p>
          <ul>
            <li>
              <a
                class="text-blue-600 hover:text-blue-800 cursor-pointer"
                href="https://github.com/APIs-guru/graphql-apis"
                target="_blank"
                >Public GraphQL-API Collection</a
              >
              (e.g.
              <a
                class="text-blue-600 hover:text-blue-800 cursor-pointer"
                href="https://api.spacex.land/graphql/"
                target="_blank"
                >SpaceX-API</a
              >)
            </li>
            <li>
              <a
                class="text-blue-600 hover:text-blue-800 cursor-pointer"
                href="https://github.com/public-apis/public-apis"
                target="_blank"
                >Public REST-API Collection</a
              >
              (e.g.
              <a
                class="text-blue-600 hover:text-blue-800 cursor-pointer"
                href="https://pokeapi.co/docs/v2"
                target="_blank"
                >Pokemon-API</a
              >)
            </li>
          </ul>
          -
        </div>
        <div class="mt-5">
          <a
            class="text-blue-600 hover:text-blue-800 cursor-pointer"
            v-on:click="showNextExercise('second')"
            >{{
              showExercise.second
                ? 'Hide the next exercise'
                : 'Show the next exercise'
            }}</a
          >
        </div>
      </section>
      <section v-if="showExercise.second" class="mt-10">
        <h2 class="font-bold text-2xl leading-6">Exercise 2</h2>
        <div class="mt-5">
          <p>
            As a second exercise you should add an global tost/notify handling
            in the already extended app. Maybe you can do this in a easy way
            with the new composition API.
          </p>
          <p>
            For example you can show a toast after something was fetched from
            the public API (which you implemented before) or also in error
            situtations.
          </p>
        </div>
        <div class="mt-5">
          <a
            class="text-blue-600 hover:text-blue-800 cursor-pointer"
            v-on:click="showNextExercise('third')"
            >{{
              showExercise.third
                ? 'Hide the next exercise'
                : 'Show the next exercise'
            }}</a
          >
        </div>
      </section>
      <section v-if="showExercise.third" class="mt-10">
        <h2 class="font-bold text-2xl leading-6">Exercise 3</h2>
        <div class="mt-5">
          <p>
            Please integrate a testing library in the current app. We're pretty
            sure that you have some components which needs to be tested.
          </p>
        </div>
      </section>
    </div>
  </div>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import { ShowExercises } from '../types/exercise'

const showExercise = reactive<ShowExercises>({
  second: false,
  third: false,
})

const showNextExercise = (exercise: keyof ShowExercises) => {
  showExercise[exercise] = !showExercise[exercise]
}
</script>
