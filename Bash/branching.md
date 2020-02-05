case "$variable" in

"$condition1")
command...
;;

"$condition2")
command...
;;

esac

select variable [in list]
do 
   command...
   break
done

