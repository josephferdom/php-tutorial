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
    
  
