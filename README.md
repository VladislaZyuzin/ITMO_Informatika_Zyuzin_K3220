# ITMO_Informatika_Zyuzin_K3220


    # Diffusion Model Card

    ## Model Information
    - **Model Type:** SimpleUNet for Diffusion
    - **Training Dataset:** CelebA (subset of 10000 images)
    - **Image Size:** 32x32
    - **Channels:** 3
    - **Parameters:** 912,611 total, 912,611 trainable

    ## Training Details
    - **Epochs:** 10
    - **Batch Size:** 8
    - **Learning Rate:** 0.0002
    - **Device:** cpu
    - **Diffusion Steps:** 500
    - **Training Time:** 0h 52m 45s

    ## Model Files
    - Final model checkpoint: `./results\diffusion_run_20250502_161612/model_epoch_10.pt`
    - Sample images: `./results\diffusion_run_20250502_161612/final_samples.png`
    
    ## Usage
    ```python
    # Load the trained model
    model = SimpleUNet(in_channels=3, out_channels=3).to(device)
    model.load_state_dict(torch.load(f"./results\diffusion_run_20250502_161612/model_epoch_10.pt")["model_state_dict"])
    
    # Create diffusion instance
    diffusion = SimpleDiffusion(
        model=model,
        num_timesteps=500,
        beta_start=0.0001,
        beta_end=0.02,
        device=device
    )
    
    # Generate samples
    samples = diffusion.sample(batch_size=4)
    ```
    
