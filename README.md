<!DOCTYPE html>
<html>
<h1>
	Report on Model Pruning using TensorFlow
</h1>


<p>
	Model pruning is used to remove neurons in the neural network which do not aide in increasing the accuracy of the desired output. By which it also decreases the model file size, and increases memory efficiency. Such a process is known as model pruning and is very useful in light weight systems.
</p>

<div>
	<h3>
		<b>
		Base Model:
	</b>
</h3>
<p>
Using the MNIST Keras dataset, creating a CNN model with 2 conv2D layers each with 16 and 32 filters respectively. The model had 12,810 trainable parameters. Trained over 4 epochs gained validation accuracy of 98% over 12,000 images. Test set got accuracy of 98.7 as, well. The model file size was 147,786 bytes

</p>
</div>

<div>
	<h3>
		<b>
		Pruned Model 1:
	</b>
	</h3>
	<p>
Created pruning_model_1, used prune_low_magnitude() method to wrap around TensorFlow model, which creates a sparse of the weights in each layer of the neural network. This wrapper takes in pruning schedule, which controls which layer to prune and the sparsity level at each step, through hyperparameters; initial_sparsity,  final_sparsity, begin_step, end_step.
For the pruning_model_1, used 50% of neurons with zero weight and end with 80% sparsity. I learnt the prune methods and techniques from TensorFlow documentation and the steps for how to implement it from the link 2.  On this model_1, gained a validation accuracy of 98.4%, trained over 2 epochs and testing accuracy of 98.5%  The final model file size of pruning_model_1 was 17,432 bytes it is almost 90% smaller in size compared to original model. 
</p>
</div>

<div>
	<h3>
		<b>
		Pruned Model 1.1(variation):
	</b>
	</h3>
	<p>
		As an experiment used above model, except used a final sparsity of 60% and same initial sparsity of 50%.Thus changing when the pruning should end gave a validation and testing accuracy being almost same, but the final model file size was 27,886 bytes, and increase of 38% from model_1 file. 
	</p>
</div>

<div>
	<h3>
		<b>
			Pruned Model 2:
		</b>
	</h3>
	<p>
		Created pruning_model_2, with similar structure except used an initial sparsity level of 30% and same final sparsity level of 80%. Hence start model with 30% of neurons with zero weights. Such a model gained a validation accuracy over 2 epochs of 98.4% and test accuracy of  98%. The final model size was 17,361 bytes, thus is was only 1% smaller in size. 
	</p>
</div>

<div>
	<p>
		Links to the TensorFlow documents used:
	</p>
	<p>
<a href="https://www.tensorflow.org/model_optimization/api_docs/python/tfmot/sparsity/keras/prune_low_magnitude">TensorFlow documentation link 1 </a>
</p>
<p>
</p>
<a href = "https://www.tensorflow.org/model_optimization/guide/pruning/pruning_with_keras">TensorFlow documentation link 2</a>
<p>
</p>
 <a href="https://www.tensorflow.org/model_optimization/guide/pruning/comprehensive_guide">TensorFlow documentation link 3</a>
</p>

</html>
