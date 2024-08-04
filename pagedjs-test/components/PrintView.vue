<template>
  <table id="section-to-print">
    <thead>
      <tr>
        <td>
          <div class="header-space">
            <h1>Header</h1>
          </div>
        </td>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <div class="content">
            <div class="article">
              <h2>Main Content</h2>

              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Rem, consectetur.</p>

              <p>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Facere, laboriosam, qui repellat sapiente iste rem natus expedita
                tempora voluptatum sit itaque. Minima eius pariatur quam esse nostrum qui neque blanditiis eum ipsam nisi quis, hic alias
                commodi distinctio aspernatur aliquid sapiente illum accusantium quos! Et, excepturi sapiente, corporis modi velit error,
                sit asperiores vitae dolorem aspernatur esse ut mollitia laudantium nobis. Suscipit vel quibusdam numquam laboriosam
                nesciunt. Dolorum vel quibusdam odit voluptatum ea repellendus, dolorem, rerum ratione suscipit numquam quidem perferendis
                vitae consequatur saepe, esse excepturi animi totam dolor. Impedit numquam beatae molestias consectetur provident ullam
                corrupti ipsa et aliquam, esse totam nesciunt labore est ducimus reiciendis autem exercitationem quas itaque laborum
                possimus harum nobis. Magnam modi cum eveniet ex incidunt deserunt exercitationem explicabo doloribus fuga minus quidem
                expedita neque officia illo sint laboriosam, ut eos corrupti est quas porro! Veniam, ut nesciunt est a atque cum ad
                asperiores ipsum nam quaerat sapiente recusandae eligendi. Libero qui animi nobis atque dolorum corporis sequi, sunt velit
                est quibusdam nostrum ad ullam repellat explicabo sit cupiditate commodi id numquam ducimus harum possimus pariatur
                obcaecati! Possimus, labore dolorum provident nam tempore illum nostrum? Nesciunt, provident similique. Nobis repellendus
                voluptatem tenetur, perspiciatis a sunt, nemo magnam enim ducimus nulla possimus, officiis aperiam. Dolores minima vitae
                hic! Officia inventore a placeat, quas facere dignissimos veniam aliquam delectus impedit eum! Sequi, et. Praesentium odio
                quaerat dignissimos qui soluta cum, molestias vitae magni autem sint magnam possimus eos architecto explicabo. Dolorum quas
                eos nulla dicta ea consequuntur architecto ab et impedit dolorem. Aperiam ipsam qui sint asperiores? Maiores beatae commodi
                aspernatur. Quisquam harum labore voluptate. Velit, laboriosam voluptate dolorum maiores reiciendis soluta maxime esse,
                tempore, assumenda molestiae consequatur et quo aperiam dolor est laborum voluptatem eos nesciunt impedit animi consectetur
                omnis ratione. Voluptatem non aperiam pariatur eligendi.
              </p>

              <div class="pagebreak"></div>
            </div>

            <div class="article">
              <table>
                <tr>
                  <th>Pos</th>
                  <th>Name</th>
                  <th>Preis</th>
                </tr>
                <tr v-for="i in 60" :key="i">
                  <td>{{ `${i}`.padStart(2, "0") }}</td>
                  <td>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nobis, quis?</td>
                  <td>{{ formatEuro(Math.round(Math.random() * 10000)) }}</td>
                </tr>
              </table>
            </div>

            <div class="article">
              <h2>Schlusstext</h2>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis, inventore atque beatae illum perferendis porro aperiam,
                facere officiis, neque alias doloribus quibusdam blanditiis ducimus debitis. Ea, explicabo, magnam veniam est, voluptatibus
                beatae corporis quas placeat quos reiciendis accusamus eaque inventore consequatur blanditiis? Aut, dolores exercitationem
                fugiat id ea deserunt aspernatur!
              </p>
            </div>
          </div>
        </td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td>
          <div class="footer-space">
            <div class="footer-content">
              <h3>Footer auf jeder Seite</h3>
            </div>
          </div>
        </td>
      </tr>
    </tfoot>
  </table>
</template>

<script setup lang="ts">
const formatEuro = new Intl.NumberFormat("de-DE", { style: "currency", currency: "EUR" }).format;

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
  /* margin: 11mm 17mm 17mm 17mm; */

  margin-bottom: 10cm;
}

#section-to-print {
  width: 210mm;
  min-height: 297mm;
  border: 1px solid black;
  padding-top: 11mm;
  padding-right: 17mm;
  padding-bottom: 17mm;
  padding-left: 17mm;
}

.pagebreak {
  border-bottom: dashed 1px black;
  margin-bottom: 1rem;
  position: relative;
  opacity: 50%;
}

.pagebreak::after {
  content: "Seitenumbruch";
  position: relative;
  display: inline-block;
  left: 50%;
  transform: translateX(-50%);
}

.header-space,
.footer-space,
.footer-content {
  height: 100px;
}

.footer-content {
  border-top: 1px solid black;
  width: 100%;
}

@media print {
  thead {
    display: table-header-group;
  }
  tfoot {
    display: table-footer-group;
  }

  .sticky {
    position: fixed;
    bottom: 0;
  }

  body {
    visibility: hidden;
  }

  .pagebreak {
    page-break-before: always;
    border-bottom: none;
    visibility: hidden;
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

  .footer-content {
    position: fixed;
    bottom: 0;
    width: calc(100% - 17mm * 2);
  }
}
</style>
