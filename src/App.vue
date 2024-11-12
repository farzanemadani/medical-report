<template>
  <table>
    <tbody>
      <tr class="page-break">
        <td>
          <div
            class="flex items-start border-b border-b-gray-400 p-2">
            <div>
              <span
                class="text-xs font-bold bg-slate-200 p-1 rounded"
                >Report Requested by</span
              >
              <span class="text-xs block mt-2"
                >Sandy Lane Pet clinic</span
              >
              <span class="text-xs block mt-2"
                >Dr.Lee Hong</span
              >
              <span class="text-xs block mt-2"
                >1 778-881-4902</span
              >
              <span class="text-xs block mt-2"
                >Lorem ipsum dolor sit amet
                consectetur</span
              >
            </div>
            <img
              class="mx-auto"
              width="100px"
              height="80px"
              src="../src/assets/logo.png" />
            <div>
              <span
                class="text-xs font-bold bg-slate-200 p-1 rounded"
                >Report Provided By</span
              >
              <span class="text-xs block"
                >ourEmail@company.com</span
              >
              <span class="text-xs block"
                >1 555 458 251</span
              >
            </div>
          </div>
          <div class="p-2 border-b border-b-gray-400">
            <div class="flex justify-between">
              <span
                class="text-md font-bold bg-slate-200 rounded p-1"
                >VWR-CASE-10062</span
              >
              <span class="text-md"
                ><strong>Submitted:</strong>10/26/2024</span
              >
              <span class="text-md"
                ><strong>ReportOn:</strong>11/9/2024</span
              >
            </div>
            <span class="block font-bold mt-2">test</span>
            <span class="block mt-2"
              >Felin | 1year 6 months 30days | Male</span
            >
          </div>
          <div class="p-2 border-b border-b-gray-400">
            <span
              class="block w-fit text-sm font-bold bg-slate-200 p-1 rounded"
              >Clinical Findings</span
            >
            <p class="text-sm py-2">
              Lorem ipsum dolor, sit amet consectetur
              adipisicing elit. Repellendus, dignissimos
              facilis ex porro impedit expedita iste rerum!
              Rerum, non enim? Ut aliquid molestias eius.
              Iusto rem voluptatum nam accusamus. Earum.
            </p>
          </div>

          <div class="py-2 border-b border-b-gray-400">
            <span
              class="text-sm p-2 rounded bg-slate-200 font-bold"
              >Radiograph Report</span
            >
            <span class="text-sm font-bold block my-3"
              >Finding</span
            >
            <p class="text-sm text-justify">
              Lorem ipsum dolor sit amet consectetur
              adipisicing elit. Exercitationem mollitia,
              aperiam illo magni, in explicabo alias minus
              similique temporibus iste recusandae molestiae
              eius voluptates aliquam ratione adipisci
              nostrum, omnis nulla! Lorem ipsum dolor sit,
              amet consectetur adipisicing elit. Quas
              tempora, illum assumenda repudiandae ab
              quibusdam maxime nihil ea fuga omnis mollitia
              odio, sed magnam suscipit deleniti minus odit
              nulla esse.
            </p>
          </div>
          <span class="text-sm font-bold"
            >Interpretation</span
          >
          <p class="text-sm text-justify my-2">
            Lorem, ipsum dolor sit amet consectetur
            adipisicing elit. Accusamus suscipit ipsam nobis
            a, repellat ullam earum, dolor, amet doloribus
            laboriosam velit alias. Commodi nostrum, dolor
            distinctio odit eum inventore mollitia. Lorem
            ipsum, dolor sit amet consectetur adipisicing
            elit. Quasi sed nostrum dolore cum soluta alias
            ipsam totam odit ratione atque nam mollitia
            voluptatem expedita tenetur error, hic maxime
            ducimus eos.
          </p>
          <span class="text-sm font-bold"
            >Recommendations</span
          >
          <p class="text-sm text-justify my-2">
            Lorem ipsum dolor sit, amet consectetur
            adipisicing elit. A, est. Rerum, sunt beatae
            numquam architecto incidunt delectus eligendi
            labore laborum quibusdam reiciendis.
            Consequuntur aspernatur impedit quos doloremque.
            Eum, deleniti sequi. Lorem ipsum dolor sit amet
            consectetur adipisicing elit. Veritatis enim
            quae rerum itaque nihil tempora voluptate ad
            exercitationem quo accusantium! Vel alias
            incidunt commodi ipsa consectetur, distinctio
            voluptatem quas excepturi!
          </p>
        </td>
      </tr>
      <tr id="images"></tr>
    </tbody>
    <tfoot class="footer">
      <tr>
        <td width="33%">&nbsp;</td>
        <td width="33%">
          <p class="text-sm">Veterinary World Radiology Inc</p>
          <p class="text-sm">Copyright@2024 - All Rights Reserved</p>
        </td>
        <td width="33%">
          <img
            width="100px"
            height="80px"
            src="../src/assets/logo.png"
            style="display: block; margin-left: auto" />
        </td>
      </tr>
    </tfoot>
  </table>
</template>

<script setup>
import { Previewer } from 'pagedjs';
import { onMounted, ref } from 'vue';
let paged = new Previewer();
const totalPages = ref(0);
paged.preview().then((flow) => {
  console.log('Rendered', flow.total, 'pages.');
});
onMounted(() => {
  const images = [
    // Array of image URLs
    'image1.png',
    'image2.png',
    'image3.png',
    'image4.png',
    'image5.png',
    'image6.png',
    'image7.png',
    'image8.png',
    'image9.png',
    'image10.png',
    'image11.png',
    'image12.png',
    'image1.png',
    'image2.png',
    'image3.png',
    'image4.png',
    'image5.png',
    'image6.png',
    'image7.png',
    'image8.png',
    'image9.png',
    'image10.png',
    'image11.png',
    'image12.png',
  ];
  const imageTable = document.getElementById('images');
  imageTable.classList.add('page-break');
  let td = document.createElement('td');
  let imageGrid = document.createElement('div');
  imageGrid.classList.add('image-grid');
  td.appendChild(imageGrid);
  imageTable.appendChild(td);

  images.forEach((src, index) => {
    const img = document.createElement('img');
    img.src = `../src/assets/${src}`;
    img.classList.add('image-frame');
    imageGrid.appendChild(img);

    if (
      (index + 1) % 10 === 0 &&
      index !== images.length - 1
    ) {
      let newRow = document.createElement('tr');
      newRow.classList.add('page-break');
      td = document.createElement('td');
      imageGrid = document.createElement('div');
      imageGrid.classList.add('image-grid');
      td.appendChild(imageGrid);
      newRow.appendChild(td);
      imageTable.parentNode.appendChild(newRow);
    }
  });

  // Append the last page break container if it has images
  if (imageGrid.children.length > 0) {
    let newRow = document.createElement('tr');
    newRow.classList.add('page-break');
    td = document.createElement('td');
    imageGrid = document.createElement('div');
    imageGrid.classList.add('image-grid');
    td.appendChild(imageGrid);
    newRow.appendChild(td);
    imageTable.parentNode.appendChild(newRow);
  }
  const lastPage = imageTable.parentNode.lastElementChild;
  const additionalContent = document.createElement('div');
  additionalContent.classList.add('last-page-content');
  additionalContent.innerHTML = `
      <span class="block font-bold text-md">Signature</span>
      <div class="flex py-2 items-center gap-x-10">
        <div class="flex items-center">
          <img width="100px" height="80px" src="../src/assets/logo.png" />
          <span class="font-bold text-lg">COMPANY FULL NAME</span>
        </div>
        <div class="flex flex-col">
          <span class="block text-md font-bold">Mark B.Taylor, Ma, DVM, DACVR</span>
          <span class="block"><strong>E:</strong> email@company.com</span>
          <span class="block"><strong>P:</strong> 45558656252</span>
        </div>
      </div>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Magni corrupti velit
        praesentium excepturi pariatur deleniti nam rem aliquam deserunt suscipit alias
        consectetur esse, accusantium, earum veniam tenetur neque odit repellat! Lorem ipsum dolor
        sit amet consectetur adipisicing elit. Blanditiis autem ipsa eum aperiam porro
        incidunt repellendus, dolorem expedita deserunt magni, magnam pariatur possimus sunt,
        rerum vel. Alias corporis officia aliquid.
      </p>
    `;
  lastPage
    .querySelector('td')
    .appendChild(additionalContent);
  const lastContent = document.querySelector(
    '.last-page-content'
  );
  const footerHeight =
    document.querySelector('.footer').offsetHeight;
  lastContent.style.position = 'absolute';
  lastContent.style.bottom = `${footerHeight + 20}px`;
});
</script>

<style>
body {
  padding: 0 !important;
}
@media print {
  tfoot {
    padding: 0 10px;
  }
  .image-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
  }
  .image-frame {
    height: 180px;
    border: 1px solid #ccc;
  }
  .footer {
    position: fixed;
    bottom: 10px;
    text-align: center;
    width: 100%;
    left: 0;
  }

  .page-break {
    page-break-after: always;
    break-after: page;
  }
  .last-page-content {
    padding: 8px;
    border-bottom: 1px solid #ccc;
  }
}
.pagedjs_page {
  margin: 0 auto !important;
}
@page {
  margin: 2mm;
  border: 1px solid #1f1c1c;
  size: A4;
  @bottom-left {
    margin-top: -15%;
    margin-left: 10px;
    content: 'Page ' counter(page) ' of ' counter(pages);
  }
}
</style>
