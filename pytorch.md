#### Load and save model
```python
torch.save({
            'epoch': epoch,
            'model_state_dict': model.state_dict(),
            'optimizer_state_dict': optimizer.state_dict(),
            'loss': loss,
            }, PATH)
           
checkpoint = torch.load(PATH)
model.load_state_dict(checkpoint['model_state_dict'])
optimizer.load_state_dict(checkpoint['optimizer_state_dict'])
epoch = checkpoint['epoch']
loss = checkpoint['loss']
```

#### Load CUDA model on CPU
```python
device = torch.device('cpu')
model = TheModelClass(*args, **kwargs)
model.load_state_dict(torch.load(PATH, map_location=device))
```

#### Print trainable arameters
```python
for name, param in model.named_parameters():
    if param.requires_grad:
        print(name, param.data.shape)
```

#### Update weights from pretrained state dict if added extra layers to the model
```python
model_dict = model.state_dict()
pretrained_dict = torch.load(PATH)

def update_weights(model_dict, pretrained_dict):
    for name, param in pretrained_dict.items():
        if name not in model_dict:
             continue
        if isinstance(param, nn.Parameter):
            # backwards compatibility for serialized parameters
            param = param.data
        model_dict[name].copy_(param)
```
