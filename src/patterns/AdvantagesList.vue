<template>
    <div class="advantage-list">
        <div class="advantage-list__col advantage-list__info">
            <div class="advantage-list__header">
                <TextStyle type="div" class="advantage-list__sub-title" variation="secondary"> {{subTitle}} </TextStyle>
                <Heading level="h2"> {{title}}</Heading>
                <Paragraph variation="large" class="advantage-list__description"> {{description}}</Paragraph>
            </div>
            <a :href="link" v-if="link && windowWidth > 1023" class="advantage-list__link">
                Learn More
                <Icon size="s" name="arrowRight" class="advantage-list__link-icon" />
            </a>
        </div>
        <div class="advantage-list__col">
            <div class="advantage-item" v-for="(item,idx) in items" :key="idx">
                <Icon v-if="item.icon" size="xxl" type="div" :name="item.icon" class="advantage-item__icon" />
                <TextStyle type="div" class="advantage-item__name"> <b>{{item.name}} </b></TextStyle>
                <Paragraph v-html="item.description" />
            </div>
        </div>
        <a :href="link" v-if="link && windowWidth <= 1023" class="advantage-list__link">
                Learn More
                <Icon size="s" name="arrowRight" class="advantage-list__link-icon" />
            </a>
    </div>
</template>

<script>
    import Heading from '@/components/Heading'
    import TextStyle from '@/components/TextStyle'
    import Paragraph from '@/components/Paragraph'
    import Icon from '@/components/Icon/Icon'


    export default {
        name: 'AdvantagesList',
        props: {
            title: {
                type: String,
                required: true
            },
            subTitle: {
                type: String
            },
            description: {
                type: String
            },
            information: {
                type: Object,
            },
            link: {
                type: String
            },
            items: {
                type: Array
            }
        },
        data() {
            return {
                windowWidth: window.innerWidth,
            }
        },
        components: {
            Heading,
            TextStyle,
            Paragraph,
            Icon
        },
        mounted() {
            window.onresize = () => {
                this.windowWidth = window.innerWidth
            };
        }

    }
</script>

<style lang="scss" scoped>
    @import "~assets/scss/config";
    @import "~assets/scss/reset";
    @import "~assets/scss/mixins";

    .advantage-list {
        padding: 64px 0;
        display: flex;

        @include respond-to(md) {
            flex-wrap: wrap;
        }

        &__col {
            flex: 2;

            @include respond-to(md) {
                flex: auto;
            }

            &:not(.advantage-list__info) {
                display: grid;
                grid-template-columns: 1fr 1fr;
                grid-gap: 56px 32px;
                @include respond-to(sm) {
                    grid-template-columns: 1fr;
                    grid-gap: 40px 0;
                }
            }
        }

        &__info {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            flex: 1;

            @include respond-to(md) {
                flex: auto;
            }
        }

        &__sub-title {
            margin-bottom: 8px;
        }

        &__description {
            margin-top: 24px;
        }

        &__link {
            font-size: 24px;
            line-height: 32px;
            color: color(link);
            margin-top: 56px;

            &-icon {
                margin-left: 16px;
            }
        }

        &__header {
            padding-right: 32px;

            @include respond-to(md) {
                padding-right: 0;
                margin-bottom: 40px;
            }
           
        }

    }

    .advantage-item {
        &__name {
            margin-bottom: 8px;
        }

        &__icon {
            margin-bottom: 16px;
        }
    }
</style>