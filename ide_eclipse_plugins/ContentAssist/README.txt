��ǿEclipse�Զ���ʾ����
=====================================
Eclipse��Ĭ��������"."������Զ���ʾ���������Ա���Զ���ʾ��������ʱ������ϣ�����������������������ĸ��ͳ����Զ���ʾ�����Խ�ʡ����������ʱ�䣨��Ȼ����ݼ�Ҳ�������ʾ��������Ҫ�ఴһ�ΰ�����̫�鷳�ˣ���

    ��Window -> preferences -> Java -> Editor -> Content assist -> Auto-Activation�£����ǿ�����"."�ź������������Ҫ�Զ���ʾ������Ļ������"ahiz"��

    Ȼ�����ǻص�Eclipse�Ŀ�������������"a"����ʾ�ͳ����ˡ�

�������ǿ��Է��֣����Auto-Activation�µ�����������ֻ������5����ĸ��Ҳ����Eclipse�Ŀ�����Ա�������������̫���Ӱ�����ܣ�������������ܲ��ðײ��ã���������Ҫ����������ơ�

��"."����������뼸���ַ�������"abij"��Ȼ��ص�����������File -> export -> general -> preferences -> ѡһ���ط����������ѡ�����C:/a.epf

���κ��ı��༭����a.epf�������ַ�����abij�����ҵ��Ժ��滻�� ��abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ_. ������֮����������������������Ȼ��ص�Eclipse��File -> import -> general -> preferences -> ����ղŵ�a.epf�ļ�����ʱ��ᷢ�������κ���ĸ�����Եõ��Զ���ʾ�ˡ�

����Զ���ʾ������ʱ����øĳ�100�������£�������Ƚ�ˬһ�㣬��Ȼ�㶼�����ˣ��Զ���ʾ�ŵ�����:)������ҲҪ���������ܡ�
======================================================
�����޸ĺ���ʾ�����.����Eclipse�����˵�������̫������..���ո�������..������ĸ����Ҳ������..�����Ҫ�޸ĵĸ����Ի�һ��.ֻ��TAB�ͻس�����(�󲿷��˵�ϰ��).
======================================================

 


�����ѡ�б��������޸�(��TAB�ͻس�����,���Ը�)
���ȣ���Eclipse����window->show view��ѡ��Plug-ins�����ҵ�org.eclipse.jface.text���Ҽ�������ѡ��import as��> Source Project��������ɺ������workspace�Ϳ��Կ������project�ˡ�
�ڵ��빤���µġ�org.eclipse.jface.text.contentassist.CompletionProposalPopup#verifyKey()����������һ�δ���

if (contains(triggers, key)) {

...

����δ����Ϊ

if (key!=0x20 && key!='=' && key!=';' && contains(triggers, key)) {

...

���а���δ���֮�ϵĴ���ע�͵�
case '/t':
e.doit= false;
fProposalShell.setFocus();
return false;
�޸�Ϊ
case '/t':
e.doit= false;
insertSelectedProposalWithMask(e.stateMask);
break;

����������������������������Ѿ��ų��˿ո��롰=����ѡ�й��ܣ�������TAB����ѡ�й��ܡ�

�����ǵ����޸ĺ�Ĳ�����Ҽ�������workspace��Ĺ��̣�ѡ��Export��>Deployable plugins and fragments�����Next��ѡ��Destinationѡ���ѡ��Directory��ѡ��һ��Ҫ��������Ŀ¼��Ȼ��Finish��Ȼ��ͻ� ������ѡ��Ŀ¼�²���һ���µ�pluginsĿ¼��������һ��jar�ļ��������滻��eclipse/plugins����� org.eclipse.jface.text_3.6.1.r361_v20100825-0800.jar(����ļ���ͬ�汾��Eclipse������ �İ汾�Ż᲻һ�������õ�Eclipse 3.6)�������ʹ󹦸���ˣ�