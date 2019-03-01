# Device-agnostic code
The trick is to define a `device` variable
```Python
device = torch.device('cuda:0' if torch.cuda.is_available() else 'cpu')
```
Now, `device` could be used with `.to` function to move models and tensors to the desired device.
```Python
model = model.to(device)
my_tensor = my_tensor.to(device)
```