
### DB->usercenter
#### modules\v1\models\Thread.php

```
 $username = Yii::$app
 ->usercenter
 ->createCommand("select username from members where uid=$uid")
 ->queryScalar();
```

---
### DB->dapp_db
#### modules\v1\models\doctor\ConsultFeeLog.php

```
public static function getDb()
{
    return Yii::$app->get('dapp_db');
}
```

---
### DB->vi_db
### modules\v1\models\Thread.php

```
282 $doctor_id = $data['doctor_id'];
$sql = "SELECT p.vi_price,p.vi_price_unit FROM vi_set_video_price p,vi_doctor_videoprice v WHERE v.set_vp_id = p.id AND v.doctor_id = $doctor_id";
$video_set = Yii::$app->vi_db->createCommand($sql)->queryOne();
$data['costfee'] = $video_set['vi_price'].'/次';
```

```
doctor_videoprice
226 $dpModel=DoctorVideoprice::find()->where(['doctor_id'=>$data['doctor_id']])->one();
```

```
set_video_price
227 $svpModel=SetVideoPrice::find()->where(['id'=>$dpModel->set_vp_id])->one();
```

```
358 $kModel=Keshi::find()->where(['kid'=>$data['keshi_id']])->one();
```


### modules\v1\controllers\ProfileController.php

```
doctor_videoprice
55 $dpModel=DoctorVideoprice::find()->where(['doctor_id'=>$doctor_id])->one();
```

```
set_video_price
57 $svpModel=SetVideoPrice::find()->where(['id'=>$dpModel->set_vp_id])->one();
```

---
### DB->jibing_db
### modules\v1\controllers\KeshiController.php

```
112:
if ($limit) {
 $secondKeshi_list = Keshi::find()->select(['kid','name','namepy'])->where(['parentid'=>$kid])->limit($limit)->asarray()->all();
} else {
 $secondKeshi_list = Keshi::find()->select(['kid','name','namepy'])->where(['parentid'=>$kid])->asarray()->all();
}

$data['keshi_name'] = Keshi::find()->where(['kid'=>$kid])->select('name')->scalar();
```
### modules\v1\models\ThreadSearch.php

```
215 $kModel=Keshi::find()->where(['kid'=>$item['keshi_id']])->one();
289 $keshiModel=Keshi::find()->where(['kid'=>$keshi_id])->one();
290 $skeshiModel=Keshi::find()->where(['kid'=>$skid])->one();
```
### modules\v1\models\doctor\Doctor.php

```
201  $keshiModel=Keshi::find()->where(['kid'=>$keshi_id])->one();
202  $skeshiModel=Keshi::find()->where(['kid'=>$skid])->one();
```

---

