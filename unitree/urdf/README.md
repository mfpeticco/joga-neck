# Simulation models (Unitree)

| File | Contents |
|---|---|
| [`joga_neck.urdf`](joga_neck.urdf) | The neck, from the Torso Mount to the camera |
| [`g1/g1_joga_neck.xml`](g1/g1_joga_neck.xml) | MuJoCo model of the Unitree G1 with the neck |

These models come from the CAD. They use the same link names, joint names, root frame, and joint zero as the [Dynamixel models](../../dynamixel/urdf/) used to train the Joga policies, and the camera pose matches the Dynamixel model to within 1 mm across the joint range. The neck is heavier (≈197 g against 154 g), mostly from the metal servos.

| Joint | Motion | Positive | Limits |
|---|---|---|---|
| `revolute_1` | yaw | look left | −90° to +90° |
| `revolute_2` | pitch | look down | −20° to +90° |

`camera_frame` is the camera pose on the OAK-1 W. In the G1 model, the neck names are prefixed with `neck_`.

```python
import mujoco
model = mujoco.MjModel.from_xml_path("unitree/urdf/g1/g1_joga_neck.xml")
```
