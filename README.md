# Yii2-DateTimeConvert
Mengubah Tanggal dan jam Asia/Jakarta

Yii2 Components Convert Date & datetime waktu Asia/Jakarta
Petunjuk Pengunaan

1. common/config/main.php
   Tambahkan pada komponen   
   'components' => [	      
		'ambilKonvesi' =>[
            'class'=>'common\components\TgljamconvertComponent',
        ],
   ],

2. Pemanggilan
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
