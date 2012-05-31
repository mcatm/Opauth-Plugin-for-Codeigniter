*Install

1. 'opauth' folder to 'third_party' folder in CI.
2. write path to plugins on controller

$this->load->add_package_path(APPPATH.'third_party/opauth/');

3. you can write config on third_party config files

$this->load->config('opauth');
$config = $this->config->item('opauth_{******}');

4. initialize library

$this->load->library('opauth', $config);

---

*Attension

- when you initialize plugin and make it not to run, you have to add 'stop' to config array. because codeigniter's constructor has no 2nd argument.
- and you have to remake around sessions in strategies. you can't use PHP native session, so you have to rewrite 'session_start()' to '$CI->load->library('session')'. (if you want, i show you my own strategy of twitter and facebook.)