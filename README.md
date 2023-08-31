## GoogleMDMClear
# Please execute this command every time after restarting the phone
`adb shell "nohup /data/local/tmp/clear_gms.sh > /data/local/tmp/clear_gms.log"`
# The default is to clean up once every 5 minutes, which is too frequent. You can modify the sleep parameter of the script to achieve a longer interval of cleaning, but please do not exceed 1.5 hours.
`while [ 1 ]; do pm clear com.google.android.gms;echo $(date); echo "clear gms success!"; sleep 300; done;` > 5 minutes
# To
`while [ 1 ]; do pm clear com.google.android.gms;echo $(date); echo "clear gms success!"; sleep 1800; done;` > 30 minutes
# If you find the reset notification popped up by gms annoying, you can turn off the notification of gms. It will not affect the functionality of the software.
`adb shell pm revoke com.google.android.gms android.permission.POST_NOTIFICATIONS`
