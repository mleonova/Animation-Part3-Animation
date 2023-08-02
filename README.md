# Animation Project: Animation

This computer animation project consists of three parts: 
 
[Part1: Skeleton](https://github.com/mleonova/Graphics-Part1-Skeleton)
 
[Part 2: Skinning](https://github.com/mleonova/Graphics-Part2-Skinning) 
 
[Part 3: Animation](https://github.com/mleonova/Graphics-Part3-Animation)

## Objectives

The main objectives of Part 3 are:

1. Load keyframe animations from (.anim) files by parsing the (.anim) file and extracting animation data, including time ranges, channels, and keyframes.

2. Implement a playback mechanism to animate a skinned character using the loaded animation. 

## Background

At its core, animation relies on the concept of a skeleton or rig, acting as an invisible framework that controls the motion of characters or objects. This skeleton is composed of interconnected joints, forming a hierarchical structure that enables animators to manipulate the character's posture and movement.

A fundamental technique in computer animation is forward kinematics. This process involves calculating the transformations of each joint in the skeleton hierarchy relative to the world coordinate system. These transformations, represented as matrices, dictate the position, rotation, and scale of each joint in 3D space. By assigning keyframes to the skeleton's joints at different time intervals, animators establish the foundation for fluid and lifelike movements.

The animation process also encompasses the concept of skinning. Skinning is the art of deforming a character's mesh (its "skin") based on the movements of the underlying skeleton. This process is achieved through a skinning algorithm that calculates the new positions of the mesh's vertices.

The final step in the animation process involves real-time rendering. Here, the program brings the animated character to life, applying lighting, shading, and other visual effects

## Animation file

```
Sample .anim file

animation {
    range [time_start] [time_end]
    numchannels [num]
    channel {
        extrapolate [extrap_in] [extrap_out]
        keys [numkeys] {
            [time] [value] [tangent_in] [tangent_out]
            ...
        }
    }
    channel {
       ...
    }
    ...
}
```

#### ```time_start``` and ```time_end```

These variables represent the time range in seconds that the animation is intended to play. The animation will be active and affect the character's motion within this time range. It's important to note that this range may not necessarily correspond to the times of the first and last keyframes in the animation.

#### ```numchannels```

This variable indicates the total number of animation channels present in the .anim file. The term "channel" here refers to a specific property or transformation being animated, such as joint rotations or translations.

#### ```channel```

This section contains the data for a single animation channel. Each channel represents a property or transformation of the character or object, and it is defined within its own curly braces.

#### ```extrapolate [extrap_in] [extrap_out]```

This line specifies the extrapolation mode for the animation channel. Extrapolation refers to how the animation behaves beyond the defined time range. The [extrap_in] variable determines the mode for the beginning of the animation (before time_start), and the [extrap_out] variable determines the mode for the end of the animation (after time_end). The extrapolation modes can be "constant," "linear," "cycle," "cycle_offset," or "bounce."

#### ```keys [numkeys]```

This line indicates the start of the keyframes section for the animation channel. The [numkeys] variable represents the total number of keyframes in this channel.

#### ```[time]```

This variable represents the time value (in seconds) of a keyframe. It specifies at which moment in the animation the particular keyframe applies.

#### ```[value]```

This variable represents the value of the property or transformation at the given keyframe time. For example, if the channel represents a joint's rotation, the [value] would be the rotation angle at that keyframe.


#### ```[tangent_in]``` and ```[tangent_out]```

These variables represent the tangent types for the keyframe. Tangents control how the animation interpolates between keyframes, determining the smoothness of the animation curve. The tangent types can be "flat," "linear," "smooth," or a floating-point slope value indicating a fixed tangent mode.

## Process


## Demo

https://github.com/mleonova/Graphics-Part3-Animation/assets/30246711/e3d949ea-6612-4762-990d-fd2fad2549ca

