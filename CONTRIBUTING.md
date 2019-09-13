# Contribuir

Este documento cobre as orientações gerais para comunicar "bugs", solicitar
funcionalidades e abrir "pull requests". Por favor, lê bem isto antes de
fazeres alguma das coisas indicadas cima!

Este projeto é regido pelo [código de conduta](CODE_OF_CONDUCT.md). Ao participares,
espera-se que o sigas o que ele estabelece. Por favor, comunica comportamentos
inaceitáveis, escrevendo para hello at chris klimas dot com.

## Comunicar um Bug

Lembra-te, por favor, que o registo de problemas serve para comunicar defeitos e
melhorias relacionados com o Chapbook. Não é um lugar para pedir ajuda sobre
como fazer alguma coisa, nem para vires resolver problemas que tenhas com a
história que estás a criar com o Chapbook--a não ser que penses que é causado
por um problema do próprio Chapbook.
Há várias comunidades online que te pode ajudar a resolver os problemas que tenhas
com a tua história. Tira partido deles.  

Be as specific as you can about bugs, and attach a story file demonstrating them
if possible. If a bug can't be reproduced on another person's computer, it can't
be fixed.

## Requesting a Feature

Please take a look at [Chapbook's design goals](DESIGN_GOALS.md) before opening
an issue--this lays out the context in which feature requests will be evaluated.

## Opening a Pull Request

**Pull requests will begin being accepted once Chapbook's 1.0.0 release is finalized.**

Pull requests should be test-coverage neutral at worst. Ideally, they improve
coverage. You can check this by running `npm run test:coverage`.

PRs should always be against the develop branch, not master.

Please open an issue to discuss a new feature before putting in the work of
implementing it. It's much better to collaboratively come up with a solution
than to have to hash it out in a PR and have to rewrite a lot of code.
