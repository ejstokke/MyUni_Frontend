<script>
    export let filterName;
    export let callAPI = true;

    let unit_list = [];
    let title = filterName;

    function changeTitle(unit) {
        console.log(unit);
    }

    async function getStudyProgramme(filterName) {
        const url = `http://127.0.0.1:5000/${filterName}`;
        await fetch(url, {
            method: 'get',
        }).then((response) => {
            return response.json();
        }).then(data => {
            unit_list = data.sort();
        });
    };

    if (callAPI) {
        getStudyProgramme(filterName);
    }
    
</script>

<div class="dropdown">
    <button class="dropbtn">{title}</button>
    <div class="dropdown-content">
        {#each unit_list as unit, i}
            <a onclick={changeTitle}>{unit}</a>
        {/each}
    </div>
</div>

<style>
    .dropbtn {
        background-color: #5DB075;
        color: white;
        padding: 16px;
        font-size: 16px;
        border: none;
        cursor: pointer;
    }

    .dropdown {
        position: relative;
        display: inline-block;
    }

    .dropdown-content {
        display: none;
        position: absolute;
        background-color: #f9f9f9;
        min-width: 160px;
        box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
        z-index: 1;
        max-height: 250px;
        overflow-y: auto;
    }

    .dropdown-content a {
        color: black;
        padding: 12px 16px;
        text-decoration: none;
        display: block;
    }

    .dropdown-content a:hover {
        background-color: #f1f1f1
    }

    .dropdown:hover .dropdown-content {
        display: block;
    }

    .dropdown:hover .dropbtn {
        background-color: #3e8e41;
    }
</style>