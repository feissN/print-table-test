<template>
  <div id="section-to-print">
    <table>
      <thead>
        <tr>
          <th>
            <div class="head">Smile</div>
          </th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>
            <div>
              <h1>Cool shit</h1>

              <div>
                <!-- content -->

                <h2>Woowie!</h2>

                <p>
                  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Autem voluptas iste doloribus quidem sequi consequuntur
                  aspernatur ipsum sed voluptatibus modi error, provident consequatur et qui delectus perspiciatis eligendi quisquam!
                  Eveniet porro necessitatibus eligendi eaque voluptas accusamus maiores sequi alias? Voluptatem alias aliquid, debitis sed
                  eveniet quis modi dicta porro dignissimos voluptatibus sapiente sequi ipsam velit consequatur eius corporis vel a
                  reprehenderit consectetur nobis amet? Fugiat veritatis vel expedita totam obcaecati esse, beatae ad eveniet, quae, magnam
                  minus libero qui ipsa neque id itaque molestiae. Aut recusandae iure ratione aliquam autem similique iste, molestiae enim
                  iusto at alias necessitatibus. Fugit, tenetur nam consequatur assumenda iste accusamus dicta tempora aut perferendis
                  rerum, sunt repellendus quis corporis a molestias dolorum rem quibusdam quia odit quisquam. Quae in unde sint quasi, ut
                  temporibus, nostrum reiciendis mollitia laboriosam maiores voluptate nam provident ipsum ratione neque ullam natus
                  corporis eos, dolore quisquam culpa est optio dolor. Officiis labore rem cum repudiandae ad hic obcaecati soluta omnis
                  velit voluptatum, aperiam dolorum quis necessitatibus inventore explicabo ipsum. Odit cumque modi possimus necessitatibus,
                  tempore dolore? Odio, amet? Fuga sapiente totam eaque necessitatibus quod? Aliquam possimus, explicabo a adipisci dolore
                  deserunt magni totam fugiat tempora excepturi nulla vel consectetur vitae!
                </p>

                <p>
                  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Autem voluptas iste doloribus quidem sequi consequuntur
                  aspernatur ipsum sed voluptatibus modi error, provident consequatur et qui delectus perspiciatis eligendi quisquam!
                  Eveniet porro necessitatibus eligendi eaque voluptas accusamus maiores sequi alias? Voluptatem alias aliquid, debitis sed
                  eveniet quis modi dicta porro dignissimos voluptatibus sapiente sequi ipsam velit consequatur eius corporis vel a
                  reprehenderit consectetur nobis amet? Fugiat veritatis vel expedita totam obcaecati esse, beatae ad eveniet, quae, magnam
                  minus libero qui ipsa neque id itaque molestiae. Aut recusandae iure ratione aliquam autem similique iste, molestiae enim
                  iusto at alias necessitatibus. Fugit, tenetur nam consequatur assumenda iste accusamus dicta tempora aut perferendis
                  rerum, sunt repellendus quis corporis a molestias dolorum rem quibusdam quia odit quisquam. Quae in unde sint quasi, ut
                  temporibus, nostrum reiciendis mollitia laboriosam maiores voluptate nam provident ipsum ratione neque ullam natus
                  corporis eos, dolore quisquam culpa est optio dolor. Officiis labore rem cum repudiandae ad hic obcaecati soluta omnis
                  velit voluptatum, aperiam dolorum quis necessitatibus inventore explicabo ipsum. Odit cumque modi possimus necessitatibus,
                  tempore dolore? Odio, amet? Fuga sapiente totam eaque necessitatibus quod? Aliquam possimus, explicabo a adipisci dolore
                  deserunt magni totam fugiat tempora excepturi nulla vel consectetur vitae!
                </p>

                <h2 class="pagebreak">Ich mach nen Page-Break!</h2>

                <table class="inner">
                  <tr>
                    <th>Pos</th>
                    <th>Name</th>
                    <th>Preis</th>
                  </tr>
                  <tr v-for="i in 30" :key="i">
                    <td>{{ i }}</td>
                    <td>Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora, officia.</td>
                    <td>100</td>
                  </tr>
                </table>

                <p>
                  Lorem ipsum dolor, sit amet consectetur adipisicing elit. Sapiente sequi repellat voluptas, aperiam, magnam iure aliquam,
                  rerum quam quidem ipsa harum a molestiae beatae dolorem atque blanditiis tempore. Repellendus et recusandae aperiam eum
                  obcaecati nisi vel accusamus modi animi fuga quidem corporis ipsam dolorum consequatur, perspiciatis autem cumque rem
                  unde.
                </p>

                <table class="inner">
                  <tr>
                    <th>Pos</th>
                    <th>Name</th>
                    <th>Preis</th>
                  </tr>
                  <tr v-for="i in 30" :key="i">
                    <td>{{ i }}</td>
                    <td>Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora, officia.</td>
                    <td>100</td>
                  </tr>
                </table>

                <p>Und nun zum abschluss</p>
                <p>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Officiis doloremque blanditiis, incidunt, quibusdam voluptates
                  quae facere architecto quo minima expedita corporis. Recusandae doloribus voluptatum fuga quos, odit suscipit ex a.
                  Aliquid voluptates consequatur, adipisci reprehenderit voluptas quisquam nostrum ea alias illum, soluta molestias
                  similique et. Voluptate animi obcaecati corrupti est sed sequi ea cum esse, totam perferendis minima praesentium vel
                  aliquam dolore facere asperiores nemo, sapiente modi quam? Explicabo iste ipsa mollitia dolorum culpa quas? Beatae numquam
                  non minima omnis! Sit inventore vel repudiandae debitis excepturi quo placeat, incidunt odit animi! Ipsa recusandae
                  temporibus doloremque repellendus optio corporis quos esse!
                </p>
              </div>
            </div>
          </td>
        </tr>
      </tbody>
      <tfoot>
        <tr>
          <td>
            <div class="foot">
              <div class="sticky">Copyright stuff</div>
            </div>
          </td>
        </tr>
      </tfoot>
    </table>
  </div>
</template>

<script setup lang="ts">
const handlePrint = () => {
  window.print();
};

defineExpose({
  handlePrint,
});
</script>

<style>
@page {
  size: A4;
  margin: 11mm 17mm 17mm 17mm;
}

#section-to-print {
  width: 210mm;
  min-height: 297mm;
  border: 1px solid black;
  /* padding-left: 2cm;
  padding-right: 2cm; */
  padding-top: 10mm;
  padding-right: 20mm;
  padding-left: 15mm;
  padding-bottom: 2cm;
}

.head {
  padding-top: 2cm;
  padding-bottom: 2cm;
}

.sticky {
  padding-bottom: 2cm;
  padding-top: 2cm;
}

.inner tr {
  background-color: chartreuse;
}

.pagebreak {
  border-bottom: 1px dashed black;
}
tfoot {
  display: table-footer-group;
}

@media print {
  .sticky {
    position: fixed;
    bottom: 0;
  }

  body {
    visibility: hidden;
  }

  .pagebreak {
    clear: both;
    page-break-after: always;
    border-bottom: none;
  }

  #section-to-print {
    visibility: visible;
    position: absolute;
    left: 0;
    top: 0;
    print-color-adjust: exact;
    padding-bottom: 4rem;
    border: none;
  }
}
</style>
