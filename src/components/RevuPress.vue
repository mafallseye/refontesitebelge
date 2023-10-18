<template>
    <HelloWorld />
    <ImageSenegal />
    <nav class="flex mb-4 px-6 py-6" aria-label="Breadcrumb">
        <ol class="inline-flex items-center space-x-1 md:space-x-3">
            <li class="inline-flex items-center">
                <a href="/"
                    class="inline-flex items-center text-sm font-medium text-gray-700 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white">
                    <svg class="mr-2 w-4 h-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z">
                        </path>
                    </svg>
                </a>
            </li>
            <li>
                <div class="flex items-center">
                    <svg class="w-6 h-6 text-gray-400" fill="currentColor" viewBox="0 0 20 20"
                        xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd"
                            d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
                            clip-rule="evenodd"></path>
                    </svg>
                    <a href="#" style="text-decoration: none;"
                        class="ml-1 text-sm font-medium text-gray-700 hover:text-gray-900 md:ml-2 dark:text-gray-400 dark:hover:text-white">Revue
                        de presse</a>
                </div>
            </li>

        </ol>
    </nav>

    <section class="bg-white dark:bg-gray-900 antialiased">
        <div class="max-w-screen-xl px-4 py-8 mx-auto lg:px-6 sm:py-16 lg:py-24">
            <div class="max-w-3xl mx-auto text-center">
                <h2
                    class="text-4xl font-extrabold leading-tight cursive tracking-tight text-red-600 dark:text-white uppercase  italic">
                    Revue de presse
                </h2>

                <div class="mt-4">
                    <!-- <a href="#" title=""
          class="inline-flex items-center text-lg font-medium text-primary-600 hover:underline dark:text-primary-500">
          Learn more about our agenda
          <svg aria-hidden="true" class="w-5 h-5 ml-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"
            fill="currentColor">
            <path fill-rule="evenodd"
              d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z"
              clip-rule="evenodd" />
          </svg>
        </a> -->
                </div>
            </div>

            <div class="flow-root max-w-3xl mx-auto mt-8 sm:mt-12 lg:mt-16 mb-10">
                <h2 class="mb-2 text-lg font-semibold text-red-600 dark:text-white cursive">RTS - JT de 20 h :</h2>
                <div class="-my-4 divide-y divide-gray-200 dark:divide-gray-700">
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            JT lundi 22 mai
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.rts.sn/actualite/detail/a-la-une/jt-20h-lundi-22-mai-2023"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        -11’25 : cérémonie d’ouverture
                                    </a>
                                </li>
                                <li>
                                    <a href="https://www.rts.sn/actualite/detail/a-la-une/jt-20h-lundi-22-mai-2023"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        -22’10 : Forafricc
                                    </a>
                                </li>
                                <li>
                                    <a href="https://www.rts.sn/actualite/detail/a-la-une/jt-20h-lundi-22-mai-2023"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        -27’00 : UCAD G3 +1
                                    </a>
                                </li>
                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            JT mercredi 24 mai
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.rts.sn/emissions/jt-20h/jt-20h-du-mercredi-24-mai-2023"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        -13’00 : Pôle de Diamniadio
                                    </a>
                                </li>
                                <li>
                                    <a href="https://www.rts.sn/emissions/jt-20h/jt-20h-du-mercredi-24-mai-2023"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        -15’28 : Foire à l’innovation
                                    </a>
                                </li>

                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            JT lundi 22 mai
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.rts.sn/actualite/detail/a-la-une/pole-urbain-diamniadio-visite-de-la-princesse-astrid"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        PÔLE URBAIN DIAMNIADIO : VISITE DE LA PRINCESSE ASTRID
                                    </a>
                                </li>
                                <li>
                                    <a href="https://www.rts.sn/actualite/detail/a-la-une/pole-urbain-diamniadio-visite-de-la-princesse-astrid"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        -41’20 Agropole centre
                                    </a>
                                </li>
                                <li>
                                    <a href="https://www.rts.sn/actualite/detail/a-la-une/pole-urbain-diamniadio-visite-de-la-princesse-astrid"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        -43’50 : Forafricc
                                    </a>
                                </li>
                                <li>
                                    <a href="https://www.rts.sn/actualite/detail/a-la-une/pole-urbain-diamniadio-visite-de-la-princesse-astrid"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        -1h 10’ 00 : Forafricc interview Youssou Ndour
                                    </a>
                                </li>
                            </ul>

                        </h3>
                    </div>






                </div>
            </div>
            <div class="flow-root max-w-3xl mx-auto mt-8 sm:mt-12 lg:mt-16 mb-10">
                <h2 class="mb-2 text-lg font-semibold text-red-600 dark:text-white cursive">Le Soleil :</h2>
                <div class="-my-4 divide-y divide-gray-200 dark:divide-gray-700">
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            24 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://lesoleil.sn/domaine-maritime-et-portuaire-le-senegal-et-la-belgique-veulent-renforcer-leur-partenariat/"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Domaine maritime et portuaire : le Sénégal et la belgique veulent renforcer leur
                                        partenariat
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>








                </div>
            </div>
            <div class="flow-root max-w-3xl mx-auto mt-8 sm:mt-12 lg:mt-16 mb-10">
                <h2 class="mb-2 text-lg font-semibold text-red-600 dark:text-white cursive">APS :</h2>
                <div class="-my-4 divide-y divide-gray-200 dark:divide-gray-700">
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            17 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://aps.sn/une-mission-economique-belge-a-dakar-du-21-au-25-mai/"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">

                                        Une mission économique belge à Dakar du 21 au 25 mai
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            23 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://aps.sn/une-foire-senegalo-belge-sur-lentrepreneuriat-a-dakar/"
                                        style="text-decoration: none;  list-style: none; color: black;">
                                        Une foire Sénégalo-belge sur l'entreprenariat, à Dakar
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            jeudi 25 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://aps.sn/des-entreprises-belges-et-senegalaises-ont-signe-40-conventions-de-partenariat-a-dakar-selon-lambassade-du-royaume/"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Des entreprises belges et sénégalaises ont signé 40 conventions de partenariat à
                                        Dakar, selon l'Ambassade du royaume
                                    </a>
                                </li>



                            </ul>

                        </h3>
                    </div>






                </div>
            </div>
            <div class="flow-root max-w-3xl mx-auto mt-8 sm:mt-12 lg:mt-16 mb-10">
                <h2 class="mb-2 text-lg font-semibold text-red-600 dark:text-white cursive">TFM :</h2>
                <div class="-my-4 divide-y divide-gray-200 dark:divide-gray-700">
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            25 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.youtube.com/watch?v=4aB_8hdoP00"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Un jour une actu : le Sénégal déroule le tapis rouge à la Princesse Astrid
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>








                </div>
            </div>
            <div class="flow-root max-w-3xl mx-auto mt-8 sm:mt-12 lg:mt-16 mb-10">
                <h2 class="mb-2 text-lg font-semibold text-red-600 dark:text-white cursive">E media TV :</h2>
                <div class="-my-4 divide-y divide-gray-200 dark:divide-gray-700">
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            24 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.youtube.com/watch?v=YNui2vIHZ2I"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Sindia: Inauguration de l'usine de chaux Carmeuse Sénégal par S.A.R la Princesse
                                        Astrid de Belgique
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>








                </div>
            </div>
            <div class="flow-root max-w-3xl mx-auto mt-8 sm:mt-12 lg:mt-16 mb-10">
                <h2 class="mb-2 text-lg font-semibold text-red-600 dark:text-white cursive">Le Quotidien :</h2>
                <div class="-my-4 divide-y divide-gray-200 dark:divide-gray-700">
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            23 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://lequotidien.sn/mission-economique-belge-a-dakar-les-opportunites-de-lagropole-centre-declinees/"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Investissements étrangers : Offensive belge au Sénégal
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            26 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://lequotidien.sn/mission-economique-belge-a-dakar-les-opportunites-de-lagropole-centre-declinees/"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Mission économique belge à Dakar : Les opportunités de l’Agropole-centre déclinées
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>







                </div>
            </div>
            <div class="flow-root max-w-3xl mx-auto mt-8 sm:mt-12 lg:mt-16 mb-10">
                <h2 class="mb-2 text-lg font-semibold text-red-600 dark:text-white cursive">Sud Quotidien :</h2>
                <div class="-my-4 divide-y divide-gray-200 dark:divide-gray-700">
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            26 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.sudquotidien.sn/partenariat-iressef-et-la-belgique-croisade-contre-les-maladies-emergentes/"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Partenariat Iressef et la Belgique : croisade contre les maladies émergentes
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            25 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.youtube.com/watch?v=7ygOQilNldY"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Une délégation d'entrepreneurs,d'hommes d'affaires et de représentants
                                        d'institutions académiques
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>








                </div>
            </div>
            <div class="flow-root max-w-3xl mx-auto mt-8 sm:mt-12 lg:mt-16 mb-10">
                <h2 class="mb-2 text-lg font-semibold text-red-600 dark:text-white cursive">Dakaractu :</h2>
                <div class="-my-4 divide-y divide-gray-200 dark:divide-gray-700">
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            Jeudi 18 Mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.dakaractu.com/La-Mission-Economique-Princiere-de-Belgique-attendue-au-Senegal-La-signature-de-30-accords-prevue-entre-les-deux-pays_a233348.html"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        La Mission Économique Princière de Belgique attendue au Sénégal : La signature de 30
                                        accords prévue entre les deux pays
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            Mercredi 24 Mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.dakaractu.com/Cooperation-bilaterale-visite-de-la-princesse-Astrid-de-Belgique-a-l-IRESSEF-pour-renforcer-le-partanariat_a233639.html"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Coopération bilatérale : visite de la princesse Astrid de Belgique à l'IRESSEF pour
                                        renforcer le partanariat.
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            27 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.youtube.com/watch?v=iScOgmb609o"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Coopération bilatérale: visite de la princesse Astrid de Belgique à l'IRESSEF en vu
                                        de renforcer leur partenariat
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>







                </div>
            </div>
            <div class="flow-root max-w-3xl mx-auto mt-8 sm:mt-12 lg:mt-16 mb-10">
                <h2 class="mb-2 text-lg font-semibold text-red-600 dark:text-white cursive">Seneweb :</h2>
                <div class="-my-4 divide-y divide-gray-200 dark:divide-gray-700">
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            25 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://seneweb.com/news/Education/cooperation-universitaire-le-g3-s-rsquo-_n_410766.html"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Coopération universitaire : Le G3 s’ouvre à l’UCAD en présence de la Princesse
                                        Astrid de Belgique
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            23 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.seneweb.com/news/Video/4eme-edition-de-la-foire-a-l-rsquo-innov_n_410619.html"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        4éme édition de la Foire à l’Innovation : Fatou Diané loue les acquis du programme «
                                        Jigeen Ñi Tamit »
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            jeudi 25 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.seneweb.com/news/Video/pole-urbain-de-diamniadio-une-delegation_n_410734.html"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Pôle Urbain de Diamniadio : Une délégation belge de l’Altesse la Princesse Astrid
                                        émerveillée par des infrastructures emblématiques
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            mercredi 24 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.seneweb.com/news/Video/sindia-son-altesse-royale-la-princesse-a_n_410711.html"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Sindia : Son Altesse Royale la Princesse Astrid de Belgique inaugure Carmeuse
                                        Sénégal, une usine ultra moderne
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            jeudi 25 mai 2023

                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.seneweb.com/news/Societe/cooperation-bilaterale-visite-de-la-prin_n_410779.html"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Coopération bilatérale : visite de la princesse Astrid de Belgique à l'IRESSEF pour
                                        renforcer le partenariat
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            jeudi 25 mai 2023

                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.seneweb.com/news/Economie/mission-economique-de-la-princesse-astri_n_410797.html"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Mission économique de la Princesse Astrid de Belgique : Plusieurs conventions
                                        signées
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">

                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            vendredi 26 mai 2023

                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">



                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://www.seneweb.com/news/Sante/cooperation-entre-l-rsquo-iressef-et-bio_n_410855.html"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Coopération entre l’IRESSEF et Bio-sourcing de Belgique : Vers la mise en place
                                        d’une unité de production de biothérapies au Sénégal
                                    </a>
                                </li>


                            </ul>

                        </h3>
                    </div>







                </div>
            </div>
            <div class="flow-root max-w-3xl mx-auto mt-8 sm:mt-12 lg:mt-16 mb-10">
                <h2 class="mb-2 text-lg font-semibold text-red-600 dark:text-white cursive">Clin d’œil Paris Match :</h2>
                <div class="-my-4 divide-y divide-gray-200 dark:divide-gray-700">
                    <div class="flex flex-col gap-2 py-4 sm:gap-6 sm:flex-row sm:items-center">
    
                        <p class="w-32 text-lg font-normal text-gray-500 sm:text-right dark:text-gray-400 shrink-0">
                            26 mai 2023
                        </p>
                        <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
    
    
    
                            <ul class="max-w-md space-y-1 text-gray-500 list-disc list-inside dark:text-gray-400"
                                style="list-style-type:none;">
                                <li>
                                    <a href="https://parismatch.com/royal-blog/princesse-astrid-de-belgique-de-lart-de-bien-porter-le-moussor-au-senegal-225581"
                                        style="text-decoration: none; list-style-type:none; list-style: none; color: black;">
                                        Princesse Astrid de Belgique : de l’art de bien porter le moussor au Sénégal
                                    </a>
                                </li>
    
    
                            </ul>
    
                        </h3>
                    </div>
    
    
    
    
    
    
    
    
                </div>
            </div>
        </div>
    </section>
    <Organisateur />
    <MyFooter />
</template>

<script>
import HelloWorld from "./HelloWorld.vue";
import ImageSenegal from "./ImageSenegal.vue";
import MyFooter from "./MyFooter.vue";
import Organisateur from "./Organisateur.vue";
export default {
    components: {
    HelloWorld,
    ImageSenegal,
    Organisateur,
    MyFooter
}

}
</script>
<style scoped>
.cursive{
 
   text-transform: uppercase;
 
}
</style>