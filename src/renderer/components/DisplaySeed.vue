<template>

	<div class="modal" :class="{'is-active': showModal}">
		<div class="modal-background" @click="closeModal"></div>
		<div class="modal-card" style="width:480px">
			<header class="modal-card-head">
				<p class="modal-card-title">{{ $t("msg.displaySeed") }}</p>
				<button class="delete" aria-label="close" @click="closeModal" ></button>
			</header>
			<section class="modal-card-body" style="height:380px;background-color: whitesmoke;">

				<p class="animated bounce has-text-weight-semibold has-text-warning" style="animation-iteration-count:3">
					{{ $t('msg.create.backupNote') }}
				</p>
<!-- Couldent figure out how to make them look like niffler-->
<!--				<div class="tags are-medium">-->
<!--					<span class="button is-primary" v-for="seed in seeds">{{seed}}</span>-->
<!--				</div>-->

				<ol>
					<li v-for="item in seeds">
						{{ item }}
					</li>
				</ol>

			</section>
		</div>
	</div>

</template>
<script>

    import { messageBus } from '@/messagebus'
    import { grinNode} from '../../shared/config'

    export default {
        name: "display-seed",
        props: {
            showModal: {
                type: Boolean,
                default: false
            }
        },
        data() {
            return {
                seeds:[],
                password: '',
				error:''
            }
        },
        beforeDestroy: function(){
            this.showModal = false
        },
        mounted() {
			this.getSeed()
        },
        methods: {
            async getSeed(){
                this.$log.info('checkpoint get seed!')

				let password = this.$walletService.getPassword()
                let seed = await this.$walletService.displaySeed(password,grinNode)

				if(!seed.seed){
				    this.error = "unable to get seed! "+seed.error
				}else{
                    this.seeds = seed.seed
				}

            },
            closeModal() {
                messageBus.$emit('close', 'windowDisplaySeed');
            }
        }
    }
</script>
<style>
	ol {
		list-style: none;
	}
	ol li::before {
		color: red;
		font-weight: bold;
	}

	ol {
		margin: 0 0 30px 20px;
		columns: 4;
		-webkit-columns: 4;
		-moz-columns: 4;
		column-gap: 30px;
		-webkit-column-gap: 30px;
		-moz-column-gap: 30px;
	}
	ol li {
		margin: 0 0 10px 0;
	}

	.center{
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
