<template lang="pug">
  nav.ContentUi.content
    h1 Hello World
    p
      | Lorem ipsum
      sup
        a [1]
      |  dolor sit amet, consectetur adipiscing elit. Nulla accumsan, metus ultrices eleifend gravida, nulla nunc varius lectus, nec rutrum justo nibh eu lectus. Ut vulputate semper dui. Fusce erat odio, sollicitudin vel erat vel, interdum mattis neque. Sub
      sub script
      |  works as well!
    h2 Second level
    p
      | Curabitur accumsan turpis pharetra
      strong augue tincidunt
      |  blandit. Quisque condimentum maximus mi, sit amet commodo arcu rutrum id. Proin pretium urna vel cursus venenatis. Suspendisse potenti. Etiam mattis sem rhoncus lacus dapibus facilisis. Donec at dignissim dui. Ut et neque nisl.
    ul
      li In fermentum leo eu lectus mollis, quis dictum mi aliquet.
      li Morbi eu nulla lobortis, lobortis est in, fringilla felis.
      li Aliquam nec felis in sapien venenatis viverra fermentum nec lectus.
      li Ut non enim metus.
    h3 Third level
    p
      | Quisque ante lacus, malesuada ac auctor vitae, congue
      a(href='#') non ante
      | . Phasellus lacus ex, semper ac tortor nec, fringilla condimentum orci. Fusce eu rutrum tellus.
    ol
      li Donec blandit a lorem id convallis.
      li Cras gravida arcu at diam gravida gravida.
      li Integer in volutpat libero.
      li Donec a diam tellus.
      li Aenean nec tortor orci.
      li Quisque aliquam cursus urna, non bibendum massa viverra eget.
      li Vivamus maximus ultricies pulvinar.
    blockquote
      | Ut venenatis, nisl scelerisque sollicitudin fermentum, quam libero hendrerit ipsum, ut blandit est tellus sit amet turpis.
    p
      | Quisque at semper enim, eu hendrerit odio. Etiam auctor nisl et
      em justo sodales
      |  elementum. Maecenas ultrices lacus quis neque consectetur, et lobortis nisi molestie.
    p
      | Sed sagittis enim ac tortor maximus rutrum. Nulla facilisi. Donec mattis vulputate risus in luctus. Maecenas vestibulum interdum commodo.
    dl
      dt Web
      dd The part of the Internet that contains websites and web pages
      dt HTML
      dd A markup language for creating web pages
      dt CSS
      dd A technology to make HTML look better
    p
      | Suspendisse egestas sapien non felis placerat elementum. Morbi tortor nisl, suscipit sed mi sit amet, mollis malesuada nulla. Nulla facilisi. Nullam ac erat ante.
    h4 Fourth level
    p
      | Nulla efficitur eleifend nisi, sit amet bibendum sapien fringilla ac. Mauris euismod metus a tellus laoreet, at elementum ex efficitur.
    pre.
      \n<!DOCTYPE html>
      <html>
        <head>
          <title>Hello World</title>
        </head>
        <body>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec viverra nec nulla vitae mollis.</p>
        </body>
      </html>
    p
      | Maecenas eleifend sollicitudin dui, faucibus sollicitudin augue cursus non. Ut finibus eleifend arcu ut vehicula. Mauris eu est maximus est porta condimentum in eu justo. Nulla id iaculis sapien.
    table
      thead
        tr
          th One
          th Two
      tbody
        tr
          td Three
          td Four
        tr
          td Five
          td Six
        tr
          td Seven
          td Eight
        tr
          td Nine
          td Ten
        tr
          td Eleven
          td Twelve
    p
      | Phasellus porttitor enim id metus volutpat ultricies. Ut nisi nunc, blandit sed dapibus at, vestibulum in felis. Etiam iaculis lorem ac nibh bibendum rhoncus. Nam interdum efficitur ligula sit amet ullamcorper. Etiam tristique, leo vitae porta faucibus, mi lacus laoreet metus, at cursus leo est vel tellus. Sed ac posuere est. Nunc ultricies nunc neque, vitae ultricies ex sodales quis. Aliquam eu nibh in libero accumsan pulvinar. Nullam nec nisl placerat, pretium metus vel, euismod ipsum. Proin tempor cursus nisl vel condimentum. Nam pharetra varius metus non pellentesque.
    h5 Fifth level
    p
      | Aliquam sagittis rhoncus vulputate. Cras non luctus sem, sed tincidunt ligula. Vestibulum at nunc elit. Praesent aliquet ligula mi, in luctus elit volutpat porta. Phasellus molestie diam vel nisi sodales, a eleifend augue laoreet. Sed nec eleifend justo. Nam et sollicitudin odio.
    figure
      img(src='https://bulma.io/images/placeholders/256x256.png')
      img(src='https://bulma.io/images/placeholders/256x256.png')
      figcaption
        | Figure 1: Some beautiful placeholders
    h6 Sixth level
    p
      | Cras in nibh lacinia, venenatis nisi et, auctor urna. Donec pulvinar lacus sed diam dignissim, ut eleifend eros accumsan. Phasellus non tortor eros. Ut sed rutrum lacus. Etiam purus nunc, scelerisque quis enim vitae, malesuada ultrices turpis. Nunc vitae maximus purus, nec consectetur dui. Suspendisse euismod, elit vel rutrum commodo, ipsum tortor maximus dui, sed varius sapien odio vitae est. Etiam at cursus metus.

</template>

<script>
export default {
  name: 'ContentUi',
}
</script>

<style lang="stylus">
// .ContentUi
</style>
