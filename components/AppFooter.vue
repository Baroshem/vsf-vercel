<template>
  <SfFooter :column="4" multiple class="footer">
    <SfFooterColumn :title="$t('About us')">
      <SfList>
        <SfListItem v-for="item in aboutUs" :key="item">
          <SfMenuItem :label="$t(item)" />
        </SfListItem>
      </SfList>
    </SfFooterColumn>
    <SfFooterColumn :title="$t('Departments')">
      <SfList>
        <SfListItem v-for="item in departments" :key="item">
          <SfMenuItem :label="$t(item)" />
        </SfListItem>
      </SfList>
    </SfFooterColumn>
    <SfFooterColumn :title="$t('Help')">
      <SfList>
        <SfListItem v-for="item in help" :key="item">
          <SfMenuItem :label="$t(item)" />
        </SfListItem>
      </SfList>
    </SfFooterColumn>
    <SfFooterColumn :title="$t('Payment & Delivery')">
      <SfList>
        <SfListItem v-for="item in paymentsDelivery" :key="item">
          <SfMenuItem :label="$t(item)" />
        </SfListItem>
      </SfList>
    </SfFooterColumn>
    <SfFooterColumn :title="$t('Social')">
      <div class="footer__socials">
        <SfImage
          class="footer__social-image"
          v-for="item in social"
          :key="item"
          :src="`/icons/${item}.webp`"
          :alt="item"
          :width="32"
          :height="32"
        />
      </div>
    </SfFooterColumn>
  </SfFooter>
</template>

<script>
import { SfFooter, SfList, SfImage, SfMenuItem } from '@storefront-ui/vue';
export default {
  components: {
    SfFooter,
    SfList,
    SfImage,
    SfMenuItem
  },
  data() {
    return {
      aboutUs: [
        this.$t('Who we are'),
        this.$t('Quality in the details'),
        this.$t('Customer Reviews')
      ],
      departments: [
        this.$t('Women fashion'),
        this.$t('Men Fashion'),
        this.$t('Kidswear'),
        this.$t('Home')
      ],
      help: [
        this.$t('Customer service'),
        this.$t('Size guide'),
        this.$t('Contact us')
      ],
      paymentsDelivery: [this.$t('Purchase terms'), this.$t('Guarantee')],
      social: ['facebook', 'pinterest', 'google', 'twitter', 'youtube'],
      isMobile: false,
      desktopMin: 1024
    };
  }
};
</script>

<style lang="scss">
.footer {
  margin-bottom: var(--spacer-xl);
  @include for-desktop {
    margin-bottom: 0;
  }
  &__socials {
    display: flex;
    justify-content: space-between;
    margin: 0 auto var(--spacer-lg);
    padding: var(--spacer-base) var(--spacer-xl);
    @include for-desktop {
      justify-content: flex-start;
      padding: var(--spacer-xs) 0;
      margin: 0 auto;
    }
  }
  &__social-image {
    margin: 0 var(--spacer-2xs) 0 0;
  }
}
.sf-footer {
  @include for-desktop {
    border-top: var(--spacer-xs) solid var(--c-primary);
    padding-bottom: 0;
    margin-top: var(--spacer-2xl);
  }
  &__container {
    padding-bottom: var(--spacer-xl);
    margin: var(--spacer-sm);
    @include for-desktop {
      max-width: 69rem;
      margin: 0 auto;
      padding-bottom: 0;
    }
  }
}
</style>