<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Sparkle,
  Tag,
  Paintbrush,
  Blocks,
  LineChart,
  Wallet,
} from "lucide-vue-next";

interface BenefitsProps {
  icon: string;
  title: string;
  description: string;
}

const benefitList: BenefitsProps[] = [
  {
    icon: "blocks",
    title: "Inovativni Sustav Upozorenja",
    description:
      "Naše sveučilište koristi najmoderniju tehnologiju za detekciju prirodnih nepogoda. Sustavi za rano upozoravanje osiguravaju pravovremene obavijesti studentima i osoblju kako bi se mogli brzo i sigurno skloniti.",
  },
  {
    icon: "lineChart",
    title: "Program Prevencije Vandalizma",
    description:
      "Implementacijom naprednih sigurnosnih kamera i sustava za prepoznavanje lica, značajno smo smanjili incidente vandalizma na našem kampusu. Suradnja s lokalnim vlastima dodatno osigurava brzo reagiranje na svaki pokušaj uništavanja imovine.",
  },
  {
    icon: "wallet",
    title: "Integrirani Sigurnosni Sustav za Tuču",
    description:
      "Naše sveučilište nudi sigurna skloništa i opsežnu podršku u slučajevima ekstremnih vremenskih uvjeta, poput tuče. Uz to, sustavi za nadzor osiguravaju brzo reagiranje na sve oblike nasilja među studentima.",
  },
  {
    icon: "sparkle",
    title: "Proaktivna Sigurnosna Strategija protiv Oružanih Prijetnji",
    description:
      "Razvili smo sveobuhvatan plan za odgovor na terorističke prijetnje koji uključuje tihi alarm, obavještavanje policije i automatsko slanje SMS obavijesti svim studentima s uputama kako se sigurno skloniti.",
  },
];

const iconMap: Record<
  string,
  | typeof Sparkle
  | typeof Tag
  | typeof Paintbrush
  | typeof Blocks
  | typeof LineChart
  | typeof Wallet
> = {
  sparkle: Sparkle,
  tag: Tag,
  paintbrush: Paintbrush,
  blocks: Blocks,
  lineChart: LineChart,
  wallet: Wallet,
};
</script>

<template>
  <section
    id="benefits"
    class="container py-24 sm:py-32"
  >
    <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
      <div>
        <h2 class="text-lg text-primary mb-2 tracking-wider">Benefiti</h2>

        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          Sigurnost na Sveučilištu
        </h2>
        <p class="text-xl text-muted-foreground mb-8">
          Na našem sveučilištu, vaša sigurnost je naš prioritet. Posvećeni smo stvaranju sigurnog okruženja aktivnim rješavanjem problema poput vandalizma, izdavanjem pravovremenih upozorenja za prirodne ili nesretne slučajeve, te osiguravanjem da ste dobro pripremljeni za svaku hitnu situaciju.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-4 w-full">
        <Card
          v-for="({ icon, title, description }, index) in benefitList"
          :key="title"
          class="bg-muted/50 dark:bg-card hover:bg-background dark:hover:bg-background transition-all delay-75 group/number"
        >
          <CardHeader>
            <CardTitle>{{ title }}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>
