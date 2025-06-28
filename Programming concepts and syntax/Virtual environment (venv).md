**Definition** 
Virtual env are created to create an isolated environment for a project. All the packages used in the project can be installed in this environment which keeps them separate from the system. 
You can use venv when you are creating a project which specifically uses a version of the packages you need which you do not wish to install on your main system. 
(Its like creating a local version of python which is isolated from the global one)

**How to create and use**
1)- Decide what package manager to use
	We'll be using [[UV package manager]] ]package manager
2)- Use `uv venv "project-name"` to create your virtual environment
3)- Use source `project-name/bin/activate` to activate the environment  
4)- You can write Which python to check your python version. it is always the one from which you created the environment
5)- now you can start installing packages and making projects. use pip list to see your packages

**TIPS**
- You can write `deactivate` to deactivate the environment 
- To delete the directory of the environment `rm -rf project-name/`
- Never create your project files inside the project 
- You can explore requirement file to learn more about  venv 

