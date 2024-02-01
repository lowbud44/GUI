# GUI
#So I am making a gui using tkinter in python, this GUI connects over wifi with a raspberry pi and runs a piece of thonny script, I would like the shell outputs from the thonny script being ran on the raspberry pi to to outputted asynchronously onto the GUI  
            for line in iter(stdout.readline, ""):
                stdout_buffer.write(line)
            output_info = stdout_buffer.getvalue()
            stdout_buffer.close()
            error = stderr.read().decode('utf-8')

            these lines display the shell outputs from the Thonny program onto the raspberry pi
            if error:
                self.result_label.config(text=f"Error: {error}", fg="red")
            else:
                self.result_label.config(text=f"Output: {output_info}", fg="green")
        except Exception as e:
            self.result_label.config(text=f"Error: {e}", fg="red")
        finally:
            ssh.close()
