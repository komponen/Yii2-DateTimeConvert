# Yii2-DateTimeConvert
Mengubah Tanggal dan jam Asia/Jakarta
Misal format: yyyy-dd-mm ke dd-mm-yyyy

Yii2 Components Convert Date & datetime waktu Asia/Jakarta
Petunjuk Pengunaan

1. Buat forlder components pada advanced\common\
2. copy file TgljamconvertComponent.php ke common\components\
3. setting pada common/config/main.php
   Tambahkan pada components   
   'components' => [	      
		'ambilKonvesi' =>[
            'class'=>'common\components\TgljamconvertComponent',
        ],
   ],

4. Pemanggilan Normal
   Untuk tanggal default:
	Yii::$app->ambilKonvesi->convert($model->start,'date');
   Untuk tanggal dan  waktu
	Yii::$app->ambilKonvesi->convert($model->start,'datetime');
   Untuk waktu
	Yii::$app->ambilKonvesi->convert($model->start,'time');
 
3. Lainya
   Yii2 menambahkan di model
       public function fields()
	{
		return [
			'tgl'=>function($model){
					return Yii::$app->ambilKonvesi->convert($model->tgl,'date');
				  },			
		];
	}
