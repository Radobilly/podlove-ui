<template lang="pug">
  div(data-test="tab-share--embed")
    h3.mb-2(:style="font") {{ $t('SHARE.EMBED.TITLE') }}
    div.flex.w-full
      input.block.text-sm.p-1.rounded-sm.mr-2.w-full.border(:aria-label="$t(inputLabel.key, inputLabel.attr)" :disabled="true" :value="embedCode" :style="{ color: contrast, background, 'border-color': brandColor }" data-test="tab-share--embed--input")
      tooltip(:content="$t('MESSAGES.COPIED')" trigger="click" @click="copyCode" :color="brandColor" :background="brandLightest" placement="top")
        button.block.px-8.py-2.text-sm.p-1.rounded-sm.mr-2.w-full.border(:title="$t(copyLabel.key, copyLabel.attr)" :style="{ color: brandColor, background, ...font, 'border-color': brandColor }")
          span(aria-hidden="true") {{ $t('SHARE.ACTIONS.COPY') }}
</template>

<script>
import { mapState } from 'redux-vuex'
import Button from '@podlove/components/button'
import InputText from '@podlove/components/input-text'
import InputSelect from '@podlove/components/input-select'
import InputGroup from '@podlove/components/input-group'
import Tooltip from '@podlove/components/tooltip'
import { selectEmbedSize } from '@podlove/player-actions/embed'
import copy from 'copy-to-clipboard'

import store from 'store'
import select from 'store/selectors'

export default {
  components: {
    ButtonComponent: Button,
    InputSelect: InputSelect,
    InputText: InputText,
    InputGroup,
    Tooltip
  },
  data: mapState({
    embedSize: select.share.embedSize,
    embedCode: select.share.code,
    font: select.theme.fontBold,
    brandColor: select.theme.brandDark,
    brandLightest: select.theme.brandLightest,
    contrast: select.theme.contrast,
    background: select.theme.alt,
    inputLabel: select.accessibility.embedCode,
    copyLabel: select.accessibility.copyEmbedLink
  }),
  methods: {
    setSize(val) {
      store.dispatch(selectEmbedSize(val))
    },

    copyCode() {
      copy(this.embedCode)
    }
  }
}
</script>
