# php-tutorial

<h3>
                <?php
                    echo (isset($_POST["meno"]) && isset($_POST["priezvisko"]) && $_POST["meno"] != "" && $_POST["priezvisko"] != "")
                        ? "Volate sa: ". $_POST["meno"] . " " . $_POST["priezvisko"]
                        : "Nezadali ste meno alebo priezvisko";
                ?>
            </h3>
            <h4>
                <?php
                    echo isset($_POST["pohlavie"]) 
                        ? "Vase pohlavie je " . $_POST["pohlavie"]
                        : "Nechcete zadavat vase pohlavie"
                ?>
            </h4>
            <h2>
                <?php
                    if (isset($_POST["farby"])){
                        echo "Oblubene farby: ";
                        foreach ($_POST["farby"] as $value)
                            echo $value . " ";
                    }
                ?>
            </h2>





<div class=" <?php 
        if(isset($_POST["vaha"]) && isset($_POST["vyska"]) && $_POST["vyska"] != "" && $_POST["vaha"] != ""){
            $BMI = vypocetBMI($_POST["vaha"], $_POST["vyska"]);
            if($BMI >= 40) echo "obese";
            elseif($BMI >= 25) echo "overweight";
            elseif($BMI >= 18.5) echo "normal";
            else echo "underweight";
        }
        else {$BMI = NULL; echo "none"; }?>">
        <h1>  
            <?php
                echo ($BMI != NULL)
                    ? "Vase BMI: $BMI"
                    : "Nezadali ste vysku alebo vahu";
            ?>
        </h1>
    </div>
    <?php
        function vypocetBMI($vaha, $vyska){
            return $vaha / (($vyska/100)**2);
        }
    ?>
    
    
    
    
    
    
    
    
    
    
    
    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Test</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <?php
        print_r($_POST);
    ?>
        <form method="POST" class="form1">
            <div class="form1-1">
                <label for="meno"> Meno: </label>
                <input type="text" name="meno" id="meno"> <br>
                <label for="priezvisko"> Priezvisko: </label>
                <input type="text" name="priezvisko" id="priezvisko"> <br>
        
                <input type="radio" name="pohlavie" id="muz" value="muz">
                <label for="muz">Muz</label><br>
                <input type="radio" name="pohlavie" id="zena" value="zena">
                <label for="zena">Zena</label>
            </div>
            <div class="form1-2">
                <label for="modra"> Modra </label>
                <input type="checkbox" name="farby[]" id="modra" value="modra"> <br>
                <label for="cervena"> Cervena </label>
                <input type="checkbox" name="farby[]" id="cervena" value="cervena"> <br>
                <label for="zelena"> Zelena </label>
                <input type="checkbox" name="farby[]" id="zelena" value="zelena"> <br>
                <label for="cierna"> Cierna </label>
                <input type="checkbox" name="farby[]" id="cierna" value="cierna"> <br>

                <input type="submit" name="osobaBtn" value="odoslat"> <br>
            </div>
        </form>
            <h3>
                <?php
                    echo (isset($_POST["meno"]) && isset($_POST["priezvisko"]) && $_POST["meno"] != "" && $_POST["priezvisko"] != "")
                        ? "Volate sa: ". $_POST["meno"] . " " . $_POST["priezvisko"]
                        : "Nezadali ste meno alebo priezvisko";
                ?>
            </h3>
            <h4>
                <?php
                    echo isset($_POST["pohlavie"]) 
                        ? "Vase pohlavie je " . $_POST["pohlavie"]
                        : "Nechcete zadavat vase pohlavie"
                ?>
            </h4>
            <h2>
                <?php
                    if (isset($_POST["farby"])){
                        echo "Oblubene farby: ";
                        foreach ($_POST["farby"] as $value)
                            echo $value . " ";
                    }
                ?>
            </h2>
    <div class="form2">
        <h1> Vypocet BMI </h1>
        <form method="POST">
           <input type="text" name="vaha" placeholder="vaha v kg"> <br>
           <input type="text" name="vyska" placeholder="vyska v cm"> <br>
           <input type="submit" name="bmiBtn" value="odoslat"> <br>
        </form>
    </div>

    <div class=" <?php 
        if(isset($_POST["vaha"]) && isset($_POST["vyska"]) && $_POST["vyska"] != "" && $_POST["vaha"] != ""){
            $BMI = vypocetBMI($_POST["vaha"], $_POST["vyska"]);
            if($BMI >= 40) echo "obese";
            elseif($BMI >= 25) echo "overweight";
            elseif($BMI >= 18.5) echo "normal";
            else echo "underweight";
        }
        else {$BMI = NULL; echo "none"; }?>">
        <h1>  
            <?php
                echo ($BMI != NULL)
                    ? "Vase BMI: $BMI"
                    : "Nezadali ste vysku alebo vahu";
            ?>
        </h1>
    </div>
    <?php
        function vypocetBMI($vaha, $vyska){
            return $vaha / (($vyska/100)**2);
        }
    ?>
</body>
</html>
  
