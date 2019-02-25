<template>
<section>
    <h2>Services</h2>
    <div>

        <aside>
            <img src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/52605786_315884945734006_8580587467558617088_n.jpg?_nc_cat=108&_nc_ht=scontent-msp1-1.xx&oh=1cfc842e8d795d96b0de4ce2bed7c246&oe=5CDA1F53">
            <img src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/50919557_304172613571906_4609286823926038528_n.jpg?_nc_cat=100&_nc_ht=scontent-msp1-1.xx&oh=c7c4201587dac845fdb36eeab8ac7acc&oe=5CDCFD57">
            <img src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/48427216_290838798238621_712726647127670784_n.jpg?_nc_cat=101&_nc_ht=scontent-msp1-1.xx&oh=cd53468ae18df2bcde2083b292c7785c&oe=5D25F254">
            <img src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/49064907_292125451443289_9190335556435836928_n.jpg?_nc_cat=111&_nc_ht=scontent-msp1-1.xx&oh=c0fa7a4a1078ae6471f1685c986277f5&oe=5D26F3EE">
            <img src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/49454807_295469391108895_5289399795805323264_n.jpg?_nc_cat=101&_nc_ht=scontent-msp1-1.xx&oh=e94291c6abcbc62cd232bcb5ac60439f&oe=5D282254">
            <img src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/49938122_299802030675631_7041744880615292928_n.jpg?_nc_cat=110&_nc_ht=scontent-msp1-1.xx&oh=8f27a868612cb4ed096427531252251f&oe=5D1EFB6D">
        </aside>
        <ul>
            <li>Call Mary for a Consultation at  
        <a href="tel:314-956-9224">314.956.9224</a><br><br>
                <h3>Haircuts & Styles</h3>
            <ol><li>
Women's Cut & Style <span>$52 and up</span></li><li>
Men's Cut & Style <span>$30 and up</span></li><li>
Children's Cut & Style (12 and under) <span>$32 and up</span></li><li>
Blowout - long hair <span>$45 and up</span></li><li>
Blowout - short hair <span>$35 and up</span></li><li>
Deva Lesson + Cut <span>$80 and up</span></li></ol>
</li>
<li>
<h3>Coloring Services</h3><ol><li>
Color Retouch + style <span>$80 and up</span></li><li>
All Over Color & Style <span>$95 and up</span></li><li>
Partial foil + Glaze <span>$115 and up</span></li><li>
Full Foil + glaze <span>$135 and up</span></li><li>
Balayage & Style <span>$160 and up</span></li><li>
Color Melt (base color + balayage) <span>$240 and up</span></li><li>
Color Retouch + Cut <span>$132 and up</span></li><li>
All Over Color + Cut <span>$147 and up</span></li><li>
Color Retouch + Partial Foil <span>$145 and up</span></li><li>
Color Retouch + Partial Foil + Cut <span>$197 and up</span></li><li>
Color Retouch + Full Foil + Style <span>$165 and up</span></li><li>
All Over Color + Partial Foil + Cut + Style <span>$227 and up</span></li><li>
Color Retouch + Full Foil + Cut + Style <span>$217 and up</span></li><li>
All Over Color + Full Foil + Cut + Style <span>$247 and up</span></li><li>
Niophlex Treatment <span>$25 and up</span></li><li>
Glazing/ Toner <span>$25 and up</span></li></ol>
</li>
<li>
<h3>Formal Design</h3><ol><li>
Dances, Evening Event, Special Occasion <span>$76 and up</span></li><li>
Bridal (Trial Run) <span>$80 and up</span></li><li>
Bridal (Day Of) <span>$100 and up</span></li><li>
Weaving/Extension Services</li><li>
Tape Extensions <span>$150 and up</span></li></ol>
</li>
<li>
<h3>Waxing Services</h3><ol><li>
Eyebrow Shaping <span>$15 and up</span></li><li>
Lip Wax <span>$10 and up</span></li><li>
Chin Wax <span>$15</span></li></ol>
</li>
        </ul>
    </div>
</section>
</template>

<script>
export default {
    transition: 'slide'
}
</script>

<style scoped>
h2 {
    overflow: hidden;
    opacity: 0;
    height: 0;
    width: 0;   
}
div {
    display: grid;
    grid-template-columns: 70% 30%;
}
ol, ul {
    list-style: none;
    padding: 0;
}
ul {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    padding-top: 2em;
}
ul > li {
    width: 100%;
}
h3 {
    font-family: 'Playfair Display';
}
ol > li {
    display: grid;
    grid-template-columns: 65% 35%;
}
span {
    display: inline-block;
}
aside {
    display: flex;
    height: calc(100vh - 57px);
    overflow: hidden;
    flex-wrap: wrap;
}
img {
    height: 50%;

}

@media screen and (max-width: 900px) {
    div {
        grid-template-columns: 35% 65%;
    }

    ul {
        padding-left: 2em;
    }
}

@media screen and (max-width: 600px) {
    div {
        grid-template-columns: 0% 100%;
    }
    ul {
        padding: 6em 2em;
    }
}
</style>
