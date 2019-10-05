/*
 * Copyright 2017-2019 Amazon.com, Inc. or its affiliates. All Rights Reserved.
 *
 * Licensed under the Apache License, Version 2.0 (the "License"). You may not use this file except in compliance with
 * the License. A copy of the License is located at
 *
 *     http://aws.amazon.com/apache2.0/
 *
 * or in the "license" file accompanying this file. This file is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR
 * CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions
 * and limitations under the License.
 */

<template>
  <div id="federatedSignIn">
    <amazon-button
      v-if="amazonClientId"
      :amazonClientId="amazonClientId"
    ></amazon-button>

    <facebook-button
      v-if="facebookAppId"
      :facebookAppId="facebookAppId"
    ></facebook-button>

    <google-button
      v-if="googleClientId"
      :googleClientId="googleClientId"
    ></google-button>
  </div>
</template>

<script>
import FacebookButton from './Provider/FacebookButton';
import GoogleButton from './Provider/GoogleButton';
import AmazonButton from './Provider/AmazonButton';
export default {
  name: 'FederatedSignIn',
  props: {
    amazonClientId: {
      type: String,
      required: false,
      default: ''
    },
    googleClientId: {
      type: String,
      required: false,
      default: ''
    },
    facebookAppId: {
      type: String,
      required: false,
      default: ''
    }
  },
  components: {
    FacebookButton,
    GoogleButton,
    AmazonButton
  }
}
</script>