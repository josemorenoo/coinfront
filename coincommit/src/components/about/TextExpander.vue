<template>
    <div class="text-expander">
        <div class="sidebar">
            <div class="sidebar-item" v-for="(item, index) in items" :key="index" @click="selectedIndex = index"
                :class="{ 'selected': selectedIndex === index }">
                {{ item.title }}
                <img class="left-arrow" src="@/assets/left_arrow.png" v-if="selectedIndex === index" />
            </div>
        </div>
        <div class="main-content">
            <div class="content-item-bold" :class="{ 'selected': selectedIndex === index }">
                {{ items[selectedIndex].bold_text }}
            </div>
            <div class="content-item-normal" :class="{ 'selected': selectedIndex === index }">
                {{ items[selectedIndex].normal_text_one }}
            </div>
            <div class="content-item-normal" :class="{ 'selected': selectedIndex === index }">
                {{ items[selectedIndex].normal_text_two }}

            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            selectedIndex: 0,
            items: [
                {
                    title: 'Why',
                    bold_text: 'In the arena of nascent cryptocurrency projects there exists immense investment potential across short to long term horizons, equalled by immense amounts of volatility in the markets.',
                    normal_text_one: 'Fear of missing out, coupled with easy access to marketing of (usually) highly-technically complex projects makes it hard for investors (many who have software development experience) to understand the technical foundations of most new crypto projects.',
                    normal_text_two: 'The crypto market as a whole adopted the same technical analysis techniques that exist for charting price action of publicly traded Web2 companies. Fundamental analysis in Web3 also exists with regards to the experience of the founders, the amount and pedigree of capital made available by backers in a project, and general market analysis of how the project could disrupt its Web2 counterparts. However, the data made available to retail investors for fundamental analysis is missing a critical component: digestible analysis of the codebase that drives the functionality and subsequently price of the cryptocurrency. We want to deeply understand the tech community’s engagement around any given project.'
                },
                {
                    title: 'What',
                    bold_text: 'Coin Commit is a set of analytics tools that allow retail investors and crypto enthusiasts to programmatically extract insights from the open-source codebases of cryptocurrencies.',
                    normal_text_one: 'For any given project, Coin Commit allows you to understand the number of developers, the number of lines of code changes, the types of files worked on (frontend, backend, config, documentation), and the tech stack of each project (programming languages and frameworks used). Units of code known as “commits” on GitHub, which is a popular code repository used in software development, can be explored and visualized as discrete events or groups of events on a time series which also displays the price of the cryptocurrency.',
                    normal_text_two: 'Over time, Coin Commit will evolve to leverage machine learning to understand what types of code changes may be indicative of future price changes, in conjunction with more typical signals like social media volume, experience of developers, and investment in projects. Users will be able to subscribe to alerts about different projects, including new features, unusual software development activity, and new notable contributors who may also be investors.'
                },
                {
                    title: 'How',
                    bold_text: 'The Coin Commit website works by maintaining a list of code repositories for a number of open-source crypto projects which are accessible on Github',
                    normal_text_one: 'Mining additional data from the historical changes of each project. Project data is scraped on a daily basis, and stored on AWS for further analysis. Notable projects with regards to different metrics (most contributors, most lines of code changed, most commits) are shared on Twitter multiple times per week.',
                    normal_text_two: ''
                },
            ]
        };
    },
};
</script>

<style>
.text-expander {
    padding-left: 25%;
    padding-right: 25%;
    background-color: #120B26;
    height: 42rem;
}

.sidebar {
    float: left;
    width: 20%;
    height: 100%;
}

.sidebar-item {
    padding: 10px;
    cursor: pointer;
    color: #FFFFFF;
    position: relative;
}

.sidebar-item.selected {
    color: #2CC3F3;
}

.left-arrow {
    position: absolute;
    top: 14px;
    right: 88px;
}

.main-content {
    float: left;
    width: 80%;
    height: 100%;
}

.content-item-bold {
    padding: 10px;
    height: auto;
    display: block;

    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 32px;
    line-height: 40px;

    color: #FFFFFF;
}

.content-item-normal {
    padding: 10px;

    height: auto;
    display: block;

    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 32px;

    color: #FFFFFF;
}
</style>