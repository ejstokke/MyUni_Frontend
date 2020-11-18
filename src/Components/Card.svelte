<script>
    export let studyCode;
    let studyName;
    let uniName;
    let category;


    function assignVariables(data) {
        studyName = data.programme_name;
        category = data.education_field;
        uniName = data.uni_code;
    }

    async function getStudyProgramme(study_code) {
        const url = `http://127.0.0.1:5000/studies?study_code=${study_code}`
        await fetch(url, {
            method: 'get',
        }).then((response) => {
            return response.json();
        }).then(data => {
            assignVariables(data);
        });
    };

    getStudyProgramme(studyCode);
</script>

<svelte:head>
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Inter&display=swap" rel="stylesheet">
</svelte:head>

<div class='card'>
    <div>
        <img src={`assets/images/${category}.jpg`} alt={studyName} />
        <p>{studyName}</p>
        <p id="subTitle">{uniName}</p>
    </div>
    <span class="bottomRow">
        <p id="category">{category}</p>
        <p id="rating">⭐{(Math.random() * 5).toFixed(1)}</p>
    </span>
    
</div>

<style>
    .card {
        background-color: white;
        border: 1px solid rgba(0, 0, 0, 0.1);
        padding: 5px;
        border-radius: 6px;
        box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
        width: 175px;
        height: 225px;
        margin: 0px 7.5px 0px 7.5px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    
    .bottomRow {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: flex-end;
    }

    img {
        width: 100%;
        height: 100px;
        border-radius: 6px;
    }

    #category {
        font-family: Inter;
        font-style: italic;
        font-weight: 200;
        color: #666666;
    }

    #rating {
        color: #666666;
        font-weight: 400;
    }

    p {
        margin: 0px;
        font-family: 'Inter', sans-serif;
        font-style: normal;
        font-weight: 600;
        font-size: 16px;
    }

    #subTitle {
        font-size: 12px;
    }
</style>