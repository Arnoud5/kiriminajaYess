<template>
    <div class="forms w-80">
        <form class="md:grid md:grid-cols-4 md:divide-x md:items-center ">
            <div class="">
                <label for="from">From</label> <br>
                <input type="text" name="from" placeholder="asal"><br>
            </div> 
            <div class="">
                <label for="destination">Destination</label><br>
                <input type="text" name="destination" placeholder="tujuan"><br>
            </div>
            <div class="">
                <label for="weight">weight</label><br>
                <input type="text" name="weight" placeholder="1000gr"><br>
            </div>
            <input class="btn-form md:p-8" type="button" value="Kirim">
        </form>
    </div>
</template>

<style lang="scss">
.forms{
    margin: 200px auto;
    box-shadow: 2px 2px 10px rgb(163, 163, 163);
    display: flex;
    flex-direction: column;
    width: 90vw;
    
    form{
        padding: 20px;

        input{
            border: none;
        }

        .btn-form{
            margin: 10px 0;
            width: 100%;
            background-color: rgb(166, 38, 216) ;
            color:white;
            font-weight: 800;
            border-radius: 10px;
        }
    }


}

</style>
