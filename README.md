pip install -r requirements.txt
pip install -e .


python train.py spacetimeformer crypto --context_points 168 --target_points 24 --d_model 100 --d_ff 400 --enc_layers 5 --dec_layers 5 --l2_coeff 1e-3 --dropout_ff .2 --dropout_emb .1 --d_qk 20 --d_v 20 --n_heads 6 --run_name spatiotemporal_al_solar --batch_size 32 --class_loss_imp 0 --initial_downsample_convs 1 --decay_factor .8 --warmup_steps 1000

python train.py spacetimeformer solar_energy --run_name spatiotemporal_al_solar --context_points 21 --target_points 6 --d_model 8 --d_ff 64 --enc_layers 2 --dec_layers 2 --l2_coeff 1e-3 --dropout_ff .2 --dropout_emb .1 --d_qk 16 --d_v 16 --n_heads 2 --batch_size 128 --class_loss_imp 0

python train.py spacetimeformer crypto --run_name crypto_test --context_points 21 --target_points 6 --d_model 8 --d_ff 64 --enc_layers 2 --dec_layers 2 --l2_coeff 1e-3 --dropout_ff .2 --dropout_emb .1 --d_qk 16 --d_v 16 --n_heads 2 --batch_size 128 --class_loss_imp 0

python train.py spacetimeformer agri --run_name test_agri --context_points 21 --target_points 6 --d_model 8 --d_ff 64 --enc_layers 2 --dec_layers 2 --l2_coeff 1e-3 --dropout_ff .2 --dropout_emb .1 --d_qk 16 --d_v 16 --n_heads 2 --batch_size 128 --class_loss_imp 0

python train.py spacetimeformer agri --run_name test_agri --max_epochs=5 --context_points 168 --target_points 24 --d_model 100 --d_ff 400 --enc_layers 5 --dec_layers 5 --l2_coeff 1e-3 --dropout_ff .2 --dropout_emb .1 --d_qk 20 --d_v 20 --n_heads 6 --batch_size 32 --class_loss_imp 0 --initial_downsample_convs 1 --decay_factor .8 --warmup_steps 1000

[Edit]
train.py
1) Num columns of dset
    if config.dset == "solar_energy"
    --> yc_dim = 9
        yt_dim = 9
2) Num columns of dset
    if config.dset == "solar_energy"
    --> target_cols