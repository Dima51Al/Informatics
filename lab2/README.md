 - Отчет по лабе 2
задача:

листинг
```shell
#!bin/bash
echo "Введите IP: "



fbin () {
i=$(($1+512))
binary=$(echo "obase=2; $i" | bc)
echo "$binary" | cut -c 2-
return "$binary" | cut -c 2-
}




read NAME_bin
array=($NAME_bin)

#замена точек на пробелы
new_array=(${array[@]//"."/" "})
#echo ${new_array[@]}



last_array=(0 0 0 0)
for i in {0..4}
do
last_array[$i]=$(fbin ${new_array[$i]})
done

#echo ${last_array[@]}

str=( ${last_array[0]}.${last_array[1]}.${last_array[2]}.${last_array[3]} )
echo $str

```

этапы выполнения:
1) считать
2) преобразовать в массив
3) написать функцию преобразования
   4) 